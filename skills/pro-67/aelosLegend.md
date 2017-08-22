---
layout: page
title: Aelos Legend skill
permalink: /skills/pro-67/aelosLegend/
---

{% include header.html color="#0b2228" img="https://assets.zenbox.ai/zenbox-icons/aelosRobot.png" title="Aelos Legend skill" summary="Customizes response for situation when unit doesn’t know what to say" %}

## Summary
This voice skill enriches the dialog with unit\'s personality and supports conversation.

## Supported languages
`English`

## Sample phrases
{% include sample.html request="What can you do?" response="Singing, dancing and acrobatics would be a piece of cake for me! <code>code: 1</code>" %}
{% include sample.html request="Introduce yourself!" response="Hi, you can call me Aelos, I am a Intelligent humanoid robot. I am small but I can do a lot of things.\ncode: 2" %}
{% include sample.html request="Where do you come from?" response="I came from a distant planet.<br/>code: 5" %}
{% include sample.html request="Are you a boy or a girl?" response="I'm a robot.&lt;br/&gt;code: 9" %}
{% include sample.html request="What's your height?" response="About 35 centimeters.

code: 20" %}

## Additional parameters
This skill requires you to fill sample responses on pre-defined questions that user can ask during the conversation.

## Integration

### Response data
This skill returns the next additional data fields in the response:

`code` - a unique code from the requirements "lejuRobotics_custom.xlsx" (see examples)