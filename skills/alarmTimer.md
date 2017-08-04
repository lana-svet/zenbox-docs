---
layout: page
title: Alarm & Timer skill
permalink: /skills/alarmTimer/
---

{% include header.html color="#008066" img="https://assets.zenbox.ai/zenbox-icons/alarmTimer.png" title="Alarm & Timer skill" summary="Wakes the user up and measures the time" %}

## Summary
This voice skill enables the user to set a timer, measuring a certain time period after the present moment, and set a single or recurring alarm.

## Sample phrases
{% include sample.html request="Set an alarm for 9 o'clock." response="The alarm has been set for 9:00 am." %}
{% include sample.html request="Wake me up a 10 pm." response="The alarm has been set for 10:00 pm." %}
{% include sample.html request="Wake me up in half an hour." response="The alarm has been set for 1:55 pm." %}
{% include sample.html request="Start a timer for 5 minutes." response="Your timer will go off in 5 minutes." %}
{% include sample.html request="Cancel!" response="The timer has been cancelled." %}

## Supported languages
`English`  
`Russian`

## Additional parameters
This skill does not require any additional parameters to enable it.

## Integration

### Actions
This skill recognises and returns one of the following actions:

`addAlarm` - add alarm to the list  
`deleteAlarm` - remove alarm from the list

### Response data
This skill returns the next additional data fields in the response:

`id` - an index of an alarm (a zero-based integer)  
`text` - text, that goes along with the alarm ringing  
`timer` - unix timestamp of a moment, when alarm should ring 