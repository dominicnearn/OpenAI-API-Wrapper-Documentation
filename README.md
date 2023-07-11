# OpenAI-API-Wrapper-Documentation

Hello, and welcome to my OpenAI api wrapper. This is an easy to use wrapper that can be used FULLY client side. No need to setup a serverside environment.  

Some technical details:

model: `gpt-3.5-turbo`

request-method: `POST`



Written by Dominic. 2023. 

*azonix*

## But what is a wrapper?

A wrapper can be thought of a candy wrapper. It wraps all the complicated code into a more simple API request that takes far less time to write and debug. This wrapper is to make it easier to users to use OpenAI's API. If you're just getting started writing post, fetch, and get functions this is a perfect place to start. 

If you require help, do not hesitate to talk to me in-person or email me at `nearnd@catlin.edu`.

You may find each API endpoint below.

## Why use my wrapper?

Setting up the relevant OpenAI code is long and tricky, especially for first time programmers! In order to make it easier for people to access these wonderful tools, I created this as makes it far easier to access these tools.

## So where is your request actually going?

1. Client/Server sends request to my backend
2. My backend will authenticate your request and convert it to the relevant statements.
3. My backend will forward your information to OpenAI. 
4. OpenAI will authenticate my request then generate the relevant information using their AI software.
5. OpenAI will send the information back, then my backend will forward that information back to you.

## Endpoints

### /gpt/gpt35/api

This API takes two arguments (prompt and key). The prompt arg is what prompt you want the AI to write or generate. The key arg is your OpenAI API key. You must get an OpenAI key to use this API. You may find instructions for generating a key will be find [here](https://help.socialintents.com/article/188-how-to-find-your-openai-api-key-for-chatgpt). If you submit an invalid argument, the API will return with an error that will tell you the error code as well as what actually went wrong. Please note that this API is versatile, but should never be used in a public setting and only used in private testing to learn more about APIs. *this is because the API key is stored client side versus serverside* A wrapper on the server side is coming soon.

An example of how you may request from the API can be found below as a function. Note that you must fill out your key manually, and set your prompt to whatever supports strings (forms, textboxes, etc.)

```js
async function requestGPT() { // This function can be renamed to anything.
    let bodyArgs = JSON.stringify({
        prompt: 'example prompt', // Place the source of your prompt or the string of your prompt in here. This is what you are asking the chat bot.
        key: '', // Place OpenAI API key in this string.
    });
    let res = await fetch('https://cs.catlin.edu/node/2023/dominic/gpt/gpt35/api', { // Requests my API with the arguments provided above.
        method: 'POST', // Reqest to the server using "POST" method.
        body: bodyArgs, // Defines the body that we filled out above.
        headers: {'Content-Type': 'application/json'} // Default headers that are sent to the server specifying what is actually being sent.
    });
    if (res.ok) { // Checks to ensure the response came back.
        let apiResponse = await response.text(); // Waits for response with await function. 
        console.log(apiResponse); // The wrapper will always respond with a string. You can do whatever you want with this now. This will log it to your web development console. You may access it through the keybind 'CTRL-SHIFT-I'.
    }
};
```

## Common errors

Error `401`: This is likely caused by an invalid API key. Ensure that your API key is encased in a string. 

Error `429`: You likely sent too many requests to the server, cool off for a few minutes then try again. If this does not fix this issue you may have ran out of tokens on your OpenAI account. It's also possible OpenAI's servers are overloaded and cannot fulfill your request.

Error `500`: This is an OpenAI issue and cannot be fixed. Wait a few hours then try again.

## Closing

You may use my wrapper for whatever, but please provide credit somewhere in your webpage or code. Thanks!

*your API key is never saved to the server. made by dominic as part of a computer science project. if you want to an API wrapped, just let me know.*

last updated: `1/6/2023` (DD/MM/YYYY)
