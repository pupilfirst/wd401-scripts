The primary goal of this introductory lesson is to enable you to incorporate ChatGPT into an application running in the Node.js environment. We'll walk through installing required packages, setting up the API keys, making a ChatGPT query, and handling the API's response in a practical, easy-to-follow manner.

> Show a signed-in ChatGPT platform account.

To follow along in this level, you'll need an account with ChatGPT, and you should visit platform.openai.com to confirm that you have some amount of balance [in your billing account](https://platform.openai.com/account/billing/overview).

When you first sign up for the ChatGPT platform, you should have been given a $5 credit - this should be more than enough for our experiments.

> Screen transitions to a code editor with the Node.js project structure displayed

The application that I'm going to edit is a server-side to-do app, similar to the one that was built in WD201. I've already made one modification here - to add a simple form to the bottom of the index page, asking users to _Use natural language to create a to-do_. Right now, it's just set up to submit the input value to the server - the handler for this form submission doesn't do anything.

> Show the functioning app, and the newly added input field and its handler in the codebase.

What we would like to have it do is to create a to-do using whatever the text the user decides to type in - basically interpret whatever the user types in just like you or I would be able to do, and then take an action based on that instruction. In this demo, we're only going to demonstrate the to-do creation part.

Alright, let's dive right in! Our first step is to install the necessary Node.js packages. Open up your terminal and make sure you're in the root of your Node.js project...

...and install the openai library by running `npm install openai`. This package will serve as the bridge between our application and the AI magic of ChatGPT.

> Terminal demonstrates the installation of the openai package

```bash
npm install openai
```

Next up: API keys! To use ChatGPT, you need access to OpenAI's API, which requires a special key. With OpenAI, you can generate these keys from [the API keys](https://platform.openai.com/api-keys). Make sure that you do not share these generated keys publicly.

> Cut to a screen showing the OpenAI sign-up process, then a blurred API key

With my API key, I'm going to store it in my `.env` file. Since I'm running this app in the development environment right now, I'll be using the `dotenv` package to give me access to this value.

> Action for video recorder: Highlight the .env file creation in the code editor and ensure the expositional text explains using 'dotenv' to manage environment variables.

```bash
# .env file (make sure this file is added to .gitignore)
OPENAI_API_KEY=your_actual_openai_api_key_here
```

```js
// In your main application file or a config file, use the 'dotenv' package to load your .env
require('dotenv').config();
```

With the `openai` package installed and our API keys set, the next step is making a simple query. Check this out. I'm going to paste in a fair bit of code here, but we'll go over everything.

> Paste in the following code:

```js
// Require the OpenAI API
const OpenAI = require("openai");

// Initialize the API client with the key from your .env
const openai = new OpenAI({
  apiKey: process.env["OPENAI_API_KEY"], // This is the default and can be omitted
});

// Function to ask ChatGPT a question
async function askChatGPT(question) {
  try {
    // Make the API call to OpenAI's servers
    const chatCompletion = await openai.chat.completions.create({
      messages: [{ role: "user", content: question }],
      model: "gpt-3.5-turbo",
    });

    // Return the response text
    return chatCompletion.choices[0].message.content;
  } catch (error) {
    // Handle the error here
    console.error("Error making a query to ChatGPT:", error);
    return null;
  }
}

// Use the function to get a response and do something with it, like adding to a to-do list
async function addTodoWithChatGPT(question) {
  const suggestion = await askChatGPT(question);

  if (suggestion) {
    console.log("Response from ChatGPT:", suggestion);
  } else {
    console.log("No response received from ChatGPT.");
  }
}
```

> Explain the various bits of code inside the pasted snippet.

Now comes the moment of truth. We'll use the `addToDoWithChatGPT` function within our `/add-natural` route handler:

```js
app.post("/add-natural", async (req, res) => {
  await addTodoWithChatGPT(req.body.naturalText);

  // You can add logic here to process the natural language input
  res.redirect("/");
});
```

> Switch back to browser.

With that in place, let's try sending in a query. It can be anything. Let's _say hello_ to the AI.

> Type in _"Hello there!"_. AI should respond appropriately.

How about something a little bit more difficult?

> Type in _"What's the capital of the world?"_. AI should give an appropriate answer.

There, an intelligent answer!

Right now, all we have done is connect our application to the OpenAI API. What we really want is to process an instruction given by a user, related to the creation of to-dos, and to convert that into an action that our application can take.

For example, if we write in the example given in the text field and submit it...

> Type in _"Prepare dinner tomorrow at 7 PM"_ and submit it

...the AI is going to interpret that and give us a recipe... which is helpful, but not what we want. We want the AI to interpret it within the context of our application and to somehow convert that into a new to-do.

So, in the next lesson, we're going to use the tools API feature to make that happen.
