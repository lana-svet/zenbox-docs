---
layout: page
title: Linza features skill
permalink: /skills/pro-211/linza/
---

{% include header.html color="#2e83cc" img="https://assets.zenbox.ai/zenbox-icons/linza.png" title="Linza features skill" summary="The Linza DVR control features" %}

## Summary
This voice skill helps you to control the Linza DVR by voice.

## Supported languages
`Russian`

## Sample phrases
{% include sample.html request="Включи звук" response="Звук включён." %}
{% include sample.html request="Выруби громкость" response="Звук выключен." %}
{% include sample.html request="Начинай записывать" response="Видеозапись включена." %}
{% include sample.html request="Поставь отметку" response="Отметка создана." %}
{% include sample.html request="Фото" response="Фото сделано." %}    
{% include sample.html request="Режим парковки" response="Режим парковки включён." %}


## Additional parameters
This skill does not require any additional parameters to enable it.

## Integration

### Request
This skill requires the request data is fulfilled with an additional fields:

`linzaState` - the current state of Linza DVR (one of "videoOn", "videoOff", "parkingModeOn")


### Actions
This skill recognises and returns one of the following actions:

`muteVolume` - mute the volume on the device  
`unmuteVolume` - turn on the volume on the device   
`startVideo` - start recording the video  
`stopVideo` - stop recording the video  
`markVideo` - make a mark in the video  
`takePhoto` - take a photo in the video  
`parkingModeOn` - turn on the parking mode  
`parkingModeOff` - turn off the parking mode 
