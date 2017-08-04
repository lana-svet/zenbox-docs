---
layout: page
title: Deezer skill
permalink: /skills/deezer/
---

{% include header.html color="#000000" img="https://assets.zenbox.ai/zenbox-icons/deezer.png" title="Deezer music skill" summary="Plays music from deezer.com" %}

## Summary
This voice skill enables the user to search over millions of tracks and control the music playing.

[Deezer music](http://deezer.com) provides an easy to use music service that allows to listen a 30 seconds of track snippets without any registration
and payments. Thus Zenbox allows to search over Deezer\'s music library by voice and plays track lists.

## Sample phrases
{% include sample.html request="Play Madonna" response="Now playing Madonna, 'Lucky Stars'" %}
{% include sample.html request="Next track" response="Now playing Madonna, 'Like a Prayer'" %}
{% include sample.html request="Play something sad" response="Now playing The Hit Co., 'Fast Car'" %}
{% include sample.html request="Stop" response="The music is off." %}
{% include sample.html request="Play rock music" response="Now playing The Rolling Stones, 'Start Me Up'" %}
{% include sample.html request="Play popular music" response="Now playing Ed Sheeran, 'Shape of You'" %}
{% include sample.html request="Is it Ed Sheeran?" response="Yes, it's Ed Sheeran, 'Shape of You'" %}
{% include sample.html request="Play relaxing music" response="Now playing Acoustic Hits, 'Chilled Jazz'" %}
{% include sample.html request="What is playing?" response="It's Acoustic Hits, 'Chilled Jazz'" %}

## Supported languages
`English`  
`Russian`

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
Each entry of `musicList` array contains a JSON object with the next fields

`stream` - the track URL  
`speech` - the text to synthesise once the track is going to be played  
`title` - the title of the track

You can use this array of Track objects to automatically playback the next track once the previous has finished.