---
layout: page
title: Deezer kids music skill
permalink: /skills/deezerKids/
---

{% include header.html color="#550022" img="https://assets.zenbox.ai/zenbox-icons/deezerKids.png" title="Deezer kids music skill" summary="Plays kids music from deezer.com" %}

## Summary
This voice skill enables the user to search over thousands of songs, suitable for kids, and control the music playing.

[Deezer music](http://deezer.com) provides an easy to use music service that allows to listen a 30 seconds of track snippets without any registration
and payments. Thus Zenbox allows to search over kids music tracks in Deezer\'s music library by voice and plays track lists.


## Sample phrases
{% include sample.html request="Play music" response="Now playing The Sing-a-long Superstars, 'Ring-a-Ring-A Roses'" %}
{% include sample.html request="Change it" response="Now playing The Sing-a-long Superstars, 'Teddy Bear's Picnic'" %}
{% include sample.html request="Play something funny" response="Now playing The Pop Party Allstars, 'Baby One More Time'" %}
{% include sample.html request="Stop" response="The music is off." %}
{% include sample.html request="Play music from cartoons" response="Now playing Rhymes 'n' Rhythm, 'I Give You To His Heart'" %}
{% include sample.html request="I want to listen to a lullaby" response="Now playing Einstein Baby Lullaby Academy, 'The Ballad of Davy Crockett'" %}

## Additional parameters
This skill does not require any additional parameters to enable it.

## Integration

### Request
This skill requires the request data is fulfilled with an additional fields:

`trackId` - the currently playing track index (a zero-based integer)  
`musicState` - the current skill state string (one of "musicOn", "musicOff", "musicPause")

### Actions
This skill recognises and returns one of the following actions:

`musicOn` - an audio player should switch on the music playback  
`musicOff` - an audio player should switch off the music playback  
`musicPause` - an audio player should pause the music playback  
`musicResume` - an audio player should resume the music playback

### Response data
This skill returns the next additional data fields in the response:

`trackId` - a currently playing track index (a zero-based integer)  
`stream` - a currently playing track URL  
`musicList` - a rest of tracks list to be played next (an array of Track objects)  

#### Track object
Each entry of `musicList` array contains a JSON object with the next fields:

`stream` - the track URL  
`speech` - the text to synthesise once the track is going to be played  
`title` - the title of the track

You can use this array of Track objects to automatically playback the next track once the previous has finished.