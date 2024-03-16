In the last lesson, we left the application with just the ability to send a prompt over to ChatGPT and to show it's response on the console.

Let's kick things up a notch by telling ChatGPT that instead of a text response, what we'd like it to do is to use a _tool_.

And we do that by defining the tools available to the model. Let's add a `tools` array to the call to `chat.completions.create`:

```js
const chatCompletion = await openai.chat.completions.create({
  messages: [{ role: "user", content: question }],
  tools: [
    {
      type: "function",
      function: {
        name: "createTodo",
        description: "Create a new to-do item",
        parameters: {
          type: "object",
          properties: {
            text: {
              type: "string",
              description: "The text of the to-do item",
            },
            dueAt: {
              type: "string",
              description: "The time the to-do item is due as ISO8601",
            },
          },
        },
      },
    },
  ],
  tool_choice: { type: "function", function: { name: "createTodo" } },
  model: "gpt-3.5-turbo",
});
```

We've made two changes here - we've added the `tools` key and we're telling ChatGPT that it's possible to call a function called `createTodo`, as an action based on the message that it receives. When making this function call, we're telling the model that we expect it to include an object with two properties - `text` - the text of the to-do item, and `dueAt`, an ISO8601 string of when a to-do item is due.

In addition to making this tool available, we're also setting the `tool_choice` key, basically forcing ChatGPT to always try to call the `createTodo` function. If we didn't set this key, it might automatically decide to respond with a text message instead of trying to call the `createTodo` function.

> Switch over to the documentation site for a moment.

Once again, the documentation for these two settings can be found in OpenAI's platform documentation - it's all well-documented with lots of examples.

> Switch back to the live web app.

Let's test this out:

> Try to add with the text _"Prepare dinner tomorrow at 7:00 PM"_.

This causes the output to now say _No response received from ChatGPT_. This is because we've instructed ChatGPT to only use the tool that we've specified.

The `content` of the `message` is now `null`, so let's inspect the response object to see what it contains:

> In `askChatGPT`, add:

In the `askChatGPT` function, let's log the message object.

```js
console.log(chatCompletion.choices[0].message);
```

We can see that `content` is indeed `null` - the model isn't writing anything as text back to us, but there is now a entry in the `tool_calls` array, and it seems to be a function call - let's inspect this `function` key:

```js
console.log(chatCompletion.choices[0].message.tool_calls[0].function);
```

There! That's kind of what we want. Inside the `function` key, we can see that ChatGPT is instructing us to call our `createTodo` function, and that the arguments for the function call should be text `Prepare dinner` and it's also given us a `dueAt` as an ISO8601 value.

There's something curious there, though. Notice how, even though I'd said `Prepare dinner at 7:00 PM tomorrow`, we're getting a timestamp from 2023. This is happening because the model doesn't know what time it is right now, in the present - it's operating based on its understanding of what time it was at the time that it was trained - when it was last updated.

So let's help it out a little by telling it what the time it is right now.

> Add a `systemPrompt` at the top-level:

I'm going to give ChatGPT a bit of context - some background information in the form of text that is going to be classified as a system prompt.

```js
const systemPrompt =
  "You are an assistant helping a user manage their to-do list. " +
  "Given a message, you should extract the to-do item from it. " +
  "The user may provide a due date along with to-do item. " +
  "To compute relative dates, assume that the current timestamp is " +
  new Date().toISOString() +
  ". ";
```

The information itself is pretty simple. I'm telling the AI what I expect it to do, and more importantly, I'm supplying it the current timestamp, and instructing it to use that timestamp whenever it's computing some sort of relative date.

> Modify the list of messages passed to `chat.completions.create`:

Let's add this prompt to the list of messages sent to ChatGPT:

```js
messages: [
  { role: "system", content: systemPrompt },
  { role: "user", content: question },
]
```

Notice how I'm adding this new content using the role `system` - this causes the model to give this message higher priority.

Let's test the same prompt once again:

> Try submitting _"Prepare dinner at 7:00 PM tomorrow"_.

Today's date is March 17, so the `dueAt` in the response looks acceptable.

With the information that model is returning right now, it's trivial to connect the output from ChatGPT to our to-do list.

First, let's return the tool call from the response, instead of the text content of a message.

```js
// Return the tool call from the response.
return chatCompletion.choices[0].message.tool_calls[0].function;
```

Next, let's update the `addTodoWithChatGPT` function to actually add the to-do to the list.

```js
// Use the function to get a response and do something with it, like adding to a to-do list
async function addTodoWithChatGPT(question) {
  const toolCall = await askChatGPT(question);

  console.log(toolCall);

  switch (toolCall.name) {
    case "createTodo":
      const arguments = JSON.parse(toolCall.arguments);

      const todo = {
        id: todos.length + 1,
        text: arguments.text,
        completed: false,
        dueAt: arguments.dueAt || null,
      };

      todos.push(todo);

      break;
    default:
      console.error("Unknown tool call:", toolCall);
  }
}
```

The changes here are pretty simple - we're doing a simple switch on the name of the tool that is in the response, parsing the arguments as JSON, and then creating a to-do using the supplied `text` and `dueAt` values, and pushing it into the array of `todos`.

Let's test this out with a few inputs!

> Test it with valid inputs.

Let's try our usual suspect: _"Prepare dinner at tomorrow at 7 PM"_.

Let's try something different: _"Remind me to buy milk next weekend, early morning"_.

That looks good!

But this is not the end of the line. What happens, for example, if the user input is ambiguous.

For example, if a user says, 'Remind me,' without specifying what, our app should be able to ask, 'What do you need to be reminded about?'

We could do that by giving an additional instruction the AI:

```js
const systemPrompt =
  "You are an assistant helping a user manage their to-do list. " +
  "Given a message, you should extract the to-do item from it. " +
  "The user may provide a due date along with to-do item. " +
  "To compute relative dates, assume that the current timestamp is " +
  new Date().toISOString() +
  ". When the input is ambiguous, ask for clarification.";
```

Of course, what this also means is that I would need to add a new function,perhaps called `askForClarification`, to the list of tools available to the AI. We'd then need to handle this tool call and show the request for clarification to the user, within the user interface.

> Switch back to the app.

What we've demonstrated here is a quick and dirty example of how we can use an AI model to quickly add a functionality that could be difficult to implement using traditional computing.

With a little bit more work, this input field could handle much more complex instructions, handling all of the operations that a user takes, such as marking to-dos as complete, deleting them, or maybe multiple kinds of operations all at once.

What if we change this text input to a voice input, and process the voice first, converting that to text, before passing it to the AI model? That could allow hands-free operation of what previously _required_ UI interaction.

What else could you do in _your_ own web application, when you consider the inclusion of abilities made possible by artificial intelligence. That's what we want you to think about.
