---
layout: page
title: Dirble radio skill
permalink: /skills/radio/
---

{% include header.html color="#a02c2c" img="https://assets.zenbox.ai/zenbox-icons/radio.png" title="Dirble radio skill" summary="Finds and turns on the radio stations" %}

## Summary
This voice skill enables the user to listen to FM radio streaming. 

[Dirble radio](https://dirble.com/) provides access to more than 3000 of radiostations of 70 genres. 


## Sample phrases
{% include sample.html request="Turn on news radio" response="Turning on News radio" %}
{% include sample.html request="Turn off the radio" response="Radio is off now." %}
{% include sample.html request="Turn on the radio" response="Name the radio station or the genre and I'll look for it." %}
{% include sample.html request="BBC News" response="Turning on BBC News" %}
{% include sample.html request="Set Sunny Florida Radio" response="Turning on Sunny Florida Radio" %}
{% include sample.html request="What is playing?" response="It's Sunny Florida Radio" %}
{% include sample.html request="Turn on news radio" response="BBC News radio" %}
{% include sample.html request="Next" response="Turning on Bruxelles-news" %}

## Additional parameters
This skill requires additional parameters to enable it:

`apiKey` - developer's access token from [Dirble](https://dirble.com/)

## Integration
### Actions
This skill recognises and returns one of the following actions:

`radioOn` - an audio player should stream radio from the specified URL  
`radioOff` - an audio player should stop streaming radio

### Response data
This skill returns the next additional data fields in the response:

`stream` - URL of FM radio stream 