---
layout: page
title: Battery status skill
permalink: /skills/battery/
---

{% include header.html color="#967d7d" img="https://assets.zenbox.ai/zenbox-icons/battery.png" title="Battery status skill" summary="Shows battery status of the device" %}

## Summary
This voice skill enables the user to get the battery status of the device.

## Supported languages
`English`, `Russian`

## Sample phrases
{% include sample.html request="How much battery do i have left?" response="The battery status is 45%." %}
{% include sample.html request="How well is the device charged?" response="The battery status is 2 out of 5." %}
{% include sample.html request="Show the battery status." response="The battery status is 30%." %}

## Additional parameters
This skill requires the following parameters to enable it:

`maxValue` - the largest possible value of battery status. If `maxValue` is equal to 100, the answer will be given in percents, otherwise it will be given as the value out of `maxValue` (e.g. "2 out of 5").

## Integration

### Actions
This skill recognises and returns one of the following actions:

`showBatteryStatus` - the device can show the battery status if possible (boolean)

### Request
This skill requires the request data is fulfilled with an additional fields:

`batteryStatus` - the value of the current battery status of the device (a zero-based integer). Should be less than or equal to the `maxValue`
