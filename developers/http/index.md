---
layout: page
title: HTTP API Guide
permalink: /developers/http/
---

{% include header.html color="#3f9b86" img="/img/chemistry.png" title="HTTP API Guide" summary="This guide shows how to use Zenbox HTTP API in your application or device" %}

The HTTP API of Zenbox enables you to send user\'s requests to your Zenbox project and receive a responses from currently enabled voice skills.
This API is the most easy to use one but has a major limitation: **it does not provide a ready-to-use speech-to-text and text-to-speech components**.
It only works with text input already obtained from one of speech-to-text service providers and returns a text to synthesise with some text-to-speech service.

Thus you have to use this API only if you have implemented the speech-to-text and text-to-speech components on your own.

{% include note.html text="It's also possible to use this API if Zenbox doesn't provide yet a complete SDK for your platform." %}

## How to use HTTP API
An HTTP API provides a single endpoint to send a text request and receive a response in format of Zenbox response data.
This endpoint is placed at `https://sdk.zenbox.ai/api/request` and accepts only a `POST` requests with `application/json` content type.

Thus you have to provide a `Content-Type` header with `application/json` value.

## Request format
Request endpoint consumes a JSON formatted requests with following format:

```json
{
    "key" : "your Zenbox project API key",
    "unit" : "a unique unit ID of your device or application",
    "query" : "a text of user's query",
    "data" : {}
}
```

### Request data field
Some voice skills of Zenbox require additional parameters to process a user\'s request.
`data` field of the request can contain a JSON object with additional data that can be passed with request to process the query.
Like current timezone offset, current location\'s latitude and longitude and so on.

Please refer to the [list of voice skills](/skills/) to discover parameters you should pass with `data` field.

## Response format
The response has the following format:

```json
{
    "query" : "a text of user's query",
    "text" : "a text of response to be synthesised",
    "action" : "an optional action recognised from the request",
    "intent" : "a recognised user's intent",
    "question" : "true if Zenbox requites to continue the conversation",
    "data" : {}
}
```

### Response data field
Some voice skills return result with additional non-speech data that should be used on the side of your code that uses Zenbox API.
For example the _Music skill_ returns the currently playing track ID and a whole tracks list.
_Alarm_ skill returns a timestamp of the next alarm signal. And so on.

The `data` frield of response may contain such JSON object with additional parameters returned by the skill that handled the user\'s query.

Please refer to the [list of voice skills](/skills/) to discover parameters each skill can return.

### Intent and action
An intent is a string language independent representation of the user\'s intention recognised by Zenbox.
It is formatted in form of `/Skill name/Intent name`.
This field is mandatory in the case of successful query processing.

{% include note.html text="An empty intent field means that Zenbox didn't recognise the user's query with any of currently enabled skills." %}


An `action` field can be filled once Zenbox recognises user\'s intent that involves some additional actions on the side of your code.
Like _Music skill_ can return `musicOn` and `musicOff` actions to signal your device to play or stop music.

Please refer to the [list of voice skills](/skills/) to discover actions and intents each skill can return.

## Sample
The possible request using `curl` console command could like this

```
curl -i \
    -H "Content-Type: application/json" \
    -X POST -d '{"key": "some project key", "unit": "1234567890", "query": "play music"}' \
    https://sdk.zenbox.ai/api/request
```

The response in this case could contain the following data

```json
{
  "query": "play music",
  "text": "Now playing Luis Fonsi, 'Despacito'.",
  "action": "musicOn",
  "intent": "/Music/Play music",
  "question": false,
  "data": {
    "trackId": 0,
    "stream": "http://e-cdn-preview-0.deezer.com/stream/0fb6a1a1e4b3940e51e8f506aadaddb2-4.mp3",
    "musicList": [
      {
        "stream": "http://e-cdn-preview-0.deezer.com/stream/0fb6a1a1e4b3940e51e8f506aadaddb2-4.mp3",
        "speech": "Now playing Luis Fonsi, 'Despacito'.",
        "title": "Despacito"
      },
      {
        "stream": "http://e-cdn-preview-4.deezer.com/stream/48d67cdebdf06b2812cf05f1c06dbdad-4.mp3",
        "speech": "Now playing Imagine Dragons, 'Thunder'.",
        "title": "Thunder"
      }
    ]
  }
}    
```

## Return codes
In case of success (even an empty) response HTTP API returns a `200 OK` status with JSON payload.  
In the case of wrong formatted request `400 Bad Request` status will be returned with a plain text of error in response body.  
In all other cases of internal errors `500 Internal Server Error` status will be returned with a plain text of error in response body.

