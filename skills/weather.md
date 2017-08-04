---
layout: page
title: Openweathermap weather skill
permalink: /skills/weather/
---

{% include header.html color="#2c89a0" img="https://assets.zenbox.ai/zenbox-icons/weather.png" title="Openweathermap weather skill" summary="Information about the weather" %}

## Summary
This voice skill enables user to get information about the weather at any location on any date two weeks ahead.

[OpenWeatherMap](https://openweathermap.org/) provides access to detailed weather and forecast information at any location in the world.


## Sample phrases
{% include sample.html request="What is the weather like today?" response="It's +47 degrees with broken clouds." %}
{% include sample.html request="Weather in Chicago next week" response="In Chicago it's +68 degrees with clear sky." %}
{% include sample.html request="And in Tokyo?" response="In Tokyo it's +61 degrees with clear sky." %}
{% include sample.html request="Is it warm tomorrow?" response="3rd June it's +48 degrees with light rain" %}
{% include sample.html request="Weather in London" response="In London it's +72 degrees with shower rain." %}
{% include sample.html request="And the day after tomorrow?" response="4th June in London it's +65 degrees with light rain" %}

## Supported languages
`English`  
`Russian`

## Additional parameters
This skill requires the following parameters to enable it:

`apiKey` - developer's API key from [OpenWeatherMap](https://openweathermap.org/) 

## Integration
### Request
This skill requires the request data is fulfilled with an additional fields:

`lat` - latitude of the user current location      
`lon` - longitude of the user current location    
