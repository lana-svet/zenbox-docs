---
layout: page
title: Simple navigation skill
permalink: /skills/pro-211/simpleNavigation/
---

{% include header.html color="#189480" img="https://assets.zenbox.ai/zenbox-icons/simpleNavigation.png" title="Simple navigation skill" summary="Helps to find address on a map" %}

## Summary
This voice skill enables the user to find the address on a map using [Yandex.Geocoder](https://tech.yandex.ru/maps/geocoder/) service. Also it can remember the user's home and work addresses.

## Supported languages
`Russian`

## Sample phrases
{% include sample.html request="Проложи маршрут до Кима 1" response="Конечная точка маршрута - Санкт-Петербург проспект КИМа, 1" %}
{% include sample.html request="Проложи маршрут до дома" response="По какому адресу Вы проживаете?" %}
{% include sample.html request="Красный проспект 17" response="Новосибирск Красный проспект, 17 - правильный ли этот адрес?" %}
{% include sample.html request="Да" response="Конечная точка маршрута - Новосибирск Красный проспект, 17" %}
{% include sample.html request="Проложи маршрут до дома" response="Конечная точка маршрута - Новосибирск Красный проспект, 17" %}


## Additional parameters
This skill does not require any additional parameters to enable it.

## Integration

### Request
This skill requires the request data is fulfilled with an additional fields:

`lat` - latitude of the user\'s current location      
`lon` - longitude of the user\'s current location    

### Actions
This skill recognises and returns one of the following actions:

`navigateToAddress` - create a new route to chosen location

### Response data
This skill returns the next additional data fields in the response:

`addressLine` - address line of the chosen location (string)  
`lat` - latitude of the chosen location       
`lon` - longitude of the chosen location 
