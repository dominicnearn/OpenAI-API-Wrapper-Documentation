# openAI-API-documentation

Hello, and welcome to my OpenAI api wrapper. This is an easy to use wrapper that can be used FULLY client side. No need to setup a serverside environment.  

Written by Dominic. 2023. 

*azonix*

## /gpt/gpt35/api

This API takes two arguments (prompt and key). The prompt arg is what prompt you want the AI to write or generate. The key arg is your OpenAI API key. You must get an OpenAI key to use this API. You may find instructions for generating a key will be find [here](https://help.socialintents.com/article/188-how-to-find-your-openai-api-key-for-chatgpt). If you submit an invalid argument, the API will return with an error that will tell you the error code as well as what actually went wrong. Please note that this API is versatile, but should never be used in a public setting and only used in private testing to learn more about APIs. *this is because the API key is stored client side versus serverside* A wrapper on the server side is coming soon.

An example of how you may request from the API can be found below as a function. Note that you must fill out your key manually, and set your prompt to whatever supports strings (forms, textboxes, etc.)

```js
async function requestGPT() { // This function can be renamed to anything.
    let mainBody = JSON.stringify({
        prompt: 'example prompt',
        key: '', // Place OpenAI API key in this string.
    });
    let response = await fetch('https://cs.catlin.edu/node/2023/dominic/gpt/gpt35/api', {
        method: "POST",
        body: mainBody,
        headers: {"Content-Type": "application/json"}
    });
    if (response.ok) {
        let apiResponse = await response.text();
        console.log(apiResponse); // The wrapper will always respond with a plain-text string.
    }
};
```

You may use my API for whatever, but please provide credit somewhere in your webpage. Thanks!

*your API key is never saved to the server. if you wish to donate please cashapp $azonix*
