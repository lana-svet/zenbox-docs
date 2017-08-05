---
layout: page
title: Date & Time skill
permalink: /skills/dateTime/
---

{% include header.html color="#803300" img="https://assets.zenbox.ai/zenbox-icons/dateTime.png" title="Date & Time skill" summary="Tells the time. Every time. Everywhere." %}

## Summary
This voice skill provides time and date information for the user's location or anywhere around the world.

## Supported languages
`English`, `Russian`

## Sample phrases
{% include sample.html request="What time is it in London now?" response="It is 05:00 PM in London now" %}
{% include sample.html request="And in Chicago?" response="It's 12:00 am in Chicago now" %}
{% include sample.html request="What date is next Monday?" response="It'll be November 28 2016, Monday" %}
{% include sample.html request="Current time" response="It's 1:23 pm" %}
{% include sample.html request="Tomorrow is Wednesday?" response="No, tomorrow is Saturday" %}
{% include sample.html request="What time will be in half an hour?" response="1:26 pm" %}
{% include sample.html request="What date was 1 year ago and 3 months ago?" response="It was May 19 2015, Tuesday" %}
{% include sample.html request="How much time do we have till midnight?" response="About 11 hours" %}
{% include sample.html request="How much time do we have till Christmas day?" response="About 4 months" %}
{% include sample.html request="What's the time difference between Rome and Prague?" response="No time difference" %}
{% include sample.html request="And between Helsinki and London?" response="Time difference between Helsinki and London is -2 hours" %}
{% include sample.html request="How late is it in Chicago if in Tokyo it's 3 a.m.?" response="When it's 3 am in Tokyo, it's 1 pm in Chicago" %}

## Additional parameters
This skill does not require any additional parameters to enable it.

## Integration
### Request
This skill requires the request data is fulfilled with an additional fields:

`offset` - time offset in the user current location  
`lat` - latitude of the user current location    
 