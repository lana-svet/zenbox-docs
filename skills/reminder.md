---
layout: page
title: Reminder skill
permalink: /skills/reminder/
---

{% include header.html color="#782121" img="https://assets.zenbox.ai/zenbox-icons/reminder.png" title="Reminder skill" summary="Never lets you forget anything important" %}

## Summary
This voice skill enables the user to create a reminder for a selected time in future or for a moment in time, specified relatively to the present moment.

## Sample phrases
{% include sample.html request="Remind me to feed the cat at 3 o'clock." response="Ok, I'll remind you 3:00 am, feed the cat." %}
{% include sample.html request="Remind me to attend the meeting at 13th November at 6:30 pm." response="Ok, I'll remind you 6:30 pm, November 13, 2017, attend the meeting." %}
{% include sample.html request="Make a reminder to feed the cat." response="When should I remind you about 'feed the cat'?" %}
{% include sample.html request="Tomorrow at 3 pm." response="Ok, I'll remind you 3:00 pm, August 25, 2017, feed the cat." %}
{% include sample.html request="Cancel!" response="The reminder has been cancelled." %}

## Supported languages
`English`  
`Russian`

## Additional parameters
This skill does not require any additional parameters to enable it.

## Integration
### Actions
This skill recognises and returns one of the following actions:

`addReminder` - add reminder to the list  
`deleteReminder` - remove reminder from the list

### Response data
This skill returns the next additional data fields in the response:

`id` - an index of an alarm (a zero-based integer)  
`text` - text, that supports the alarm ring  
`timer` - unix timestamp of a moment, when alarm should ring 