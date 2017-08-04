---
layout: page
title: Volume control skill
permalink: /skills/volumeControl/
---

{% include header.html color="#ff7f2a" img="https://assets.zenbox.ai/zenbox-icons/volumeControl.png" title="Volume control skill" summary="Difference of values between each two neighbor volume levels." %}

## Summary
This volume skill enables the user to ser up and control the volume of the device. 

## Sample phrases
{% include sample.html request="Make the sound more quiet" response="Volume is decreased." %}
{% include sample.html request="Turn down" response="Volume is muted." %}
{% include sample.html request="Turn the sound on" response="Volume is unmuted." %}
{% include sample.html request="Louder" response="Volume is increased." %}
{% include sample.html request="More" response="Volume is increased." %}
{% include sample.html request="Louder" response="Volume is on the maximum level." %}
{% include sample.html request="Turn volume to minimum" response="Volume is on the minimum level." %}
{% include sample.html request="Quiter" response="Volume is muted." %}

## Supported languages
`English`  
`Russian`

## Additional parameters
This skill requires the following parameters to enable it:

`levels` - number of volume levels in your system  
`step` - difference of values between each two neighbor volume levels

## Integration
### Actions
This skill recognises and returns one of the following actions

`changeVolume` - the device should change the volume to the `currentVolume` level

### Response data
This skill returns the next additional data fields in the response

`currentVolume` - the value, which volume should be changed to (a zero-based integer)