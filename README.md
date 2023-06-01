# openAI-API-documentation

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
        console.log(apiResponse); // The default is to log the response. The response will always respond with a string. Nev
    }
};```
