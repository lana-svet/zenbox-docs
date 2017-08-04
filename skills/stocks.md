---
layout: page
title: Stock Market skill
permalink: /skills/stocks/
---

{% include header.html color="#438d77" img="https://assets.zenbox.ai/zenbox-icons/stocks.png" title="Stock Market skill" summary="Information about the stock market" %}

## Summary
This voice skill enables the user to find out the stock price of big companies. 

[Alpha Vantage](https://www.alphavantage.co/) provides stocks information about more than 3000 companies. 

## Sample phrases
{% include sample.html request="Apple's stock symbol and trading volume." response="The stock symbol is AAPL for Apple Inc. Trading volume is 24423643" %}
{% include sample.html request="Show me its market cap." response="The market cap is $749.39B for Apple Inc." %}
{% include sample.html request="What about Facebook?" response="The market cap is $436.41B for Facebook, Inc." %}
{% include sample.html request="" response="AAPL price" %}
{% include sample.html request="The closing price is 143.74 USD for Apple Inc." response="Show me the highest price of Apple on Monday." %}
{% include sample.html request="The highest price on 26th June is 148.28 USD for Apple Inc." response="And on Tuesday." %}

## Supported languages
`English`  
`Russian`

## Additional parameters
This skill requires the following parameters to enable it:

`apikey` - developer's API key from [Alpha Vantage](https://www.alphavantage.co/)

## Integration
Integration of this skill does not require any configuration setup.