---
layout: page
title: News skill
permalink: /skills/news/
---

{% include header.html color="#aa4400" img="https://assets.zenbox.ai/zenbox-icons/news.png" title="News skill" summary="Everything important" %}

## Summary
This voice skill enables user to ask for the fresh news.

[News API](https://newsapi.org/) provides the access to more than 50 news resources of 10 categories. News skill returns one-sentence snippet, which contains the most important information.


## Sample phrases
{% include sample.html request="Tell me sport news" response="LeBron James leads Cleveland to historic comeback win." %}
{% include sample.html request="Share with me news from CNN" response="Trump defies globe to claim a political win. Do you want to hear more about it?" %}
{% include sample.html request="Sure" response="Donald Trump pulled out of the Paris climate accord, one of the few major campaign promises on foreign policy he's kept. The news are supplied by NewsApi.org ." %}
{% include sample.html request="News about science" response="Watch Explorers Track Struggling Polar Bears Across Siberia." %}
{% include sample.html request="Next" response="Amazing Pictures Show Life In One of Earth's Oldest Deserts." %}
{% include sample.html request="Tell me about technology" response="Google plans to clean up the web with Chrome ad blocker next year." %}
{% include sample.html request="What source is it?" response="This information comes from 'The Verge'." %}
{% include sample.html request="What is new about politics?" response="Ted Cruz Busts Elon Musk for Flying Private Jet While Lecturing Trump on Global Warming Breitbart." %}
{% include sample.html request="When was it published?" response="This information was published on 2nd June." %}

## Additional parameters
This skill requires the following parameters to enable it:

`apiKey` - developer's access token from [News API](https://newsapi.org/)

## Integration
Integration of this skill does not require any configuration setup.