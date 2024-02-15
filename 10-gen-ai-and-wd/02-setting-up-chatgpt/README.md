# Setting up ChatGPT

Welcome back, future web developers! Today, we're stepping into the world of AI by integrating ChatGPT into our Node.js to-do application. I'll guide you through the process, and by the end of this module, your app will be having intelligent conversations with an AI. Exciting, right? Don't forget, you can always ask your AI assistant to dig deeper into any of the topics we cover.

First, let's cover the objectives of our lesson. Today's primary goal is enabling you to incorporate ChatGPT into a Node.js environment. We'll walk through installing required packages, setting up the API keys, making a ChatGPT query, and handling the API's responses and errors in a practical, easy-to-follow manner.

> Show a signed-in ChatGPT platform account.

To follow along in this level, you'll need an account with ChatGPT, and you should visit platform.openai.com to confim that you have some amount of balance [in your billing account](https://platform.openai.com/account/billing/overview).

When you first sign up for the ChatGPT platform, you should have been given a $5 credit - this should be more than enough for our experiments.

> Screen transitions to a code editor with the Node.js project structure displayed

Alright, let's dive right in! Our first step is to install the necessary Node.js packages. Open up your terminal and make sure you're in the root of your Node.js project. Got it? Great!

Now, let's install the openai library by running `npm install openai`. This package will serve as the bridge between our application and the AI magic of ChatGPT.

> Terminal demonstrates the installation of the openai package

```bash
npm install openai
```

Next up: API keys! To use ChatGPT, you need access to OpenAI's API, which requires a special key. Make sure you sign up at the OpenAI platform and protect these keys. Do not share them publicly.

> Cut to a screen showing the OpenAI sign-up process, then a blurred API key

Once you have your API keys, store them in an `.env` file. This is crucial for keeping them secure. Remember, this file should not be committed to your version control system - you don't want these keys getting out.

> Action for video recorder: Highlight the .env file creation in the code editor and ensure the expositional text explains using 'dotenv' to manage environment variables.

```bash
# .env file (make sure this file is added to .gitignore)
OPENAI_API_KEY=your_actual_openai_api_key_here
```

```js
// In your main application file or a config file, use the 'dotenv' package to load your .env
require('dotenv').config();
```

With the `openai` package installed and our API keys set, the next step is making a simple query. Check this out.

> Show the script of making a ChatGPT query with the `openai` client

We will create a function called `askChatGPT` that takes a question. Inside, we'll use the OpenAI client to send the question to ChatGPT and wait for the enlightening answer.

> Showcase the code being written with corresponding voiceover

```js
// Require the OpenAI API
const { Configuration, OpenAIApi } = require('openai');

// Initialize the API client with the key from your .env
const configuration = new Configuration({
  apiKey: process.env.OPENAI_API_KEY,
});

const openai = new OpenAIApi(configuration);

// Function to ask ChatGPT a question
async function askChatGPT(question) {
  try {
    // Make the API call to OpenAI's servers
    const response = await openai.createCompletion("text-davinci-003", {
      prompt: question,
      max_tokens: 150,
    });

    // Return the response text
    return response.data.choices[0].text;
  } catch (error) {
    // Handle the error here
    console.error('Error making a query to ChatGPT:', error);
    return null;
  }
}

// Use the function to get a response and do something with it, like adding to a to-do list
async function addToDoWithChatGPT(question) {
  const suggestion = await askChatGPT(question);

  if (suggestion) {
    console.log('Response from ChatGPT:', suggestion);
  } else {
    console.log('No response received from ChatGPT.');
  }
}
```

Now comes the moment of truth. We'll use the `addToDoWithChatGPT` function within our to-do app—for example, to get suggestions about a task. Let's run our app and see it in action.

> Action for video recorder: Use the `addToDoWithChatGPT` from the console to ask the AI to generate a list of to-dos for a complex task, and show the output from the AI.

See the response? ChatGPT offers a detailed and natural answer. Now this isn't an output that we can use directly in the application. We'll delve into that particular detail in the next lesson.

One thing we need to keep in mind is that working with APIs isn't always smooth sailing. We need to handle potential hiccups like rate limits and API errors.

But no worries, we'll wrap our API call with a try-catch block to manage these errors gracefully. Just another skill for your developer toolkit.

> Show error handling code being implemented

```js
try {
  // ... API call to OpenAI
} catch (error) {
  // Handle the error here, log it, maybe return a default message, and so on.
  console.error('Error making a query to ChatGPT:', error);
  // Possible handling for different types of errors, like rate limit exceeded
  if (error.response && error.response.status === 429) {
    console.error('Rate limit exceeded. Please try again later.');
  }
  // ...
}
```

Remember, the world of APIs is intricate. The better you handle potential issues, the sturdier your application becomes. That's all for today's lesson! You've successfully empowered your Node.js app with AI using ChatGPT.

In the next lesson, we're going switch to using the assistants API that will make it much simpler for us to design AI agents that have a specific purpose, and also to integrate it into our application.
