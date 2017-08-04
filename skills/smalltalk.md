---
layout: page
title: Smalltalk skill
permalink: /skills/smallTalk/
---

{% include header.html color="#668000" img="https://assets.zenbox.ai/zenbox-icons/smallTalk.png" title="Smalltalk skill" summary="Customizes response for situation when unit doesn’t know what to say" %}

## Summary
This voice skill enriches the dialog with unit's personality and supports conversation, when user's phrase is not associated with any of chosen skills.


## Sample phrases
{% include sample.html request="Who are you?" response="I'm a robot." %}
{% include sample.html request="How are you?" response="I am fine." %}
{% include sample.html request="How old are you?" response="I am a very young robot. I was born this year." %}
{% include sample.html request="Are you a girl?" response="Robots are neither boys nor girls." %}
{% include sample.html request="How clever you are!" response="All my intelligence is artificial." %}
{% include sample.html request="Who created you?" response="I've been created by Just AI." %}

## Additional parameters
This skill requires the following parameters to enable it:

`unitAcquaintance` - Customize response for questions like "Who you are?"  
`unitName` - Customize response for questions like "What is your name?"    
`unitAge` - Customize response for questions like "How old are you?"  
`greetingsHowAreYou` - Customize response for questions like "How are you?"     
`appraisalThankYou` - Customize response for requests like "Thank you!"           
`greetingsBye` - Customize response for requests like "Bye!"  
`greetingsHello` - Customize response for requests like "Hello!"        
`userILikeYou` - Customize response for requests like "I like you!"     
`unitGender` - Customize response for questions like "Are you a woman?"     
`unitAuthor` - Customize response for questions like "Who's created you?"        
`unitWhatAreYouDoing` -Customize response for questions like "What are you doing?"  
`unitWhatCanYouDo` - Customize response for questions like "What can you do?"   
`dialogYouDontUnderstand` - Customize response for requests like "You don't understand me."     
`dialogAffront` - Customize response for requests like "Kiss my ***."     
`unitFamily` - Customize response for questions like "Do you have a family?"        
`appraisalGood` - Customize response for requests like "Good!"  
`unitYouAreStupid` - Customize response for requests like "You are stupid!"        
`unitYouAreClever` - Customize response for requests like "You are clever!"     
`unitWhatDoYouLike` - Customize response for questions like "What do you like?"     
`appraisalYouAreWelcome` - Customize response for requests like "You are welcome!"   
`fallback` - Customize response for situation when unit doesn’t know what to say   

## Integration
Integration of this skill does not require any configuration setup.

