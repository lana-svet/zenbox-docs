---
layout: page
title: Users Guide
permalink: /users/
---

{% include header.html color="#2b4658" img="/img/ufo.png" title="Users Guide" summary="This guide shows how to start using Zenbox in your product" %}

This guide is a step-by-step introduction to zenbox.ai  
It shows how it can be useful for your product and describes a core principles of Zenbox.
You do not have to write any programming code during this guide.
There is a separate [guide for developers](/developers/) who are responsible for the integration of Zenbox SDK into the source code of your product.

## What Zenbox is about
Zenbox is a feature centric cloud platform for device manufacturers who want to enable their product to speak with end customers naturally 
using speech technologies.

Zenbox includes a ready-for-use components like speech-to-text, text-to-speech and natural language processing engine to provide you with 
comprehensive solution for building of talking products.

It doesn\'t matter what your device is.
It can be a robot, kid toy, smart speaker or even a coffee machine.
Speech capabilities could be integrated everywhere using Zenbox.

{% include note.html text="Your device should only have microphones, speakers and internet connection to be a voice enabled." %}

## Why to make your device talking
Voice control engages customers much more today than any other feature.
Moreover it is a new way of human-machine communication interface that simplifies a lot of tasks like the device usage patterns learning.

## Why Zenbox
In comparision with another solutions, Zenbox provides not only a speech-to-text recognition, text-to-speech synthesis and natural language understanding services.
It contains all these components together clued in proper way in a single bundle as well as an extensible [list of ready-for-use voice skills](/skills/)
that can be enabled for your product out of the box without needing the implementation routine.

Thus you can create a ready-for-use voice enabled project in a minutes _without any programming_ and then integrate it into the real devices 
with our easy-to-use [Zenbox SDK and API](/developers/) in days instead of months.

## How to start
Zenbox provides a web interface named [Zenbox Dashboard](https://sdk.zenbox.ai) that enables you to manage your voice projects, it\'s skills and view usage statistics.

To start with Zenbox Dashboard just sign in with an appropriate account (like Facebook or Github).
Dashboard will prompt you to create the first project.

{% include note.html text="Project is a named set of voice skills and settings of your talking device." %}

### How to create a new Zenbox Project
Once you click on "Create a new project" button, Zenbox will start a step-by-step wizard that helps to create a new project.

<img src="/img/wizard.png" width="100%" />

This wizard will guide you through a set of questions and suggest to enable a couple of the most appropriate voice skills.

{% include note.html text="The voice skill is a particular voice feature for your product. Like Music, Weather and etc." %}

## Dashboard components
After the project was created you can see a dashboard that allows to manage that project\'s skills, view statistics, try test queries and manage settings.

### Try it
The first thing to do is to try how your project understands the queries regarding the set of enabled voice skills.
Click on _Try_ link on the navigation bar at the top of the page.
The evaluation page will be opened. Here you can send your test queries and see how the project reacts.

{% include note.html text="If you use Chrome browser you can send a voice queries and receive a speech replies." %}

### Download a demo app
Demo application allows to test your project through a voice commands right from the regular Android device.
Click on _Demo_ link on the navigation bar at the top of the page.
Click then on _Download_ button to download the demo application for Android device.

{% include note.html text="You can send the Download button link to anybody else and open it right on the device to simplify the installation process." %}

The demo application will automatically connect to your Zenbox project without any authorisation and you will be able to speak with it to test all enabled skills.

## How to manage skills
Each skill is a voice feature for your project.
You can enable and disable these skills on the _Skills_ page of you project dashboard.

Some skills can have additional parameters you have to provide to enable it.
For example a weather skill can request you to provide the weather provider\'s API key.
Each skill also contains a set of example phrases that will be processed by this skill accordingly.

{% include note.html text="Note that each skill has the price per unit." %}

You can refer to the list of supported skills on the [skills page](/skills/) of this documentation.

### Custom skills
Of course your project can require some additional voice skills unique for your product.
That is why Zenbox provides you with options to add such skills to the project.

Click on _Create custom skill_ on the _Skills_ page of your dashboard.
Zenbox will provide you with multiple solutions of adding a new customised skill: create Q&A skill or request a development of the all new skill.

#### Request a skill
If you need to create a complex skill that involves some non-trivial logic or has to process a complex dialogues, just click on _Request a skill_ 
button and send us a request with desired skill description.
Our engineering stuff will reply soon to proceed with customised skill development.
Once the skill is ready to use, it will appear on the same _Skills_ page you already use to manage your project\'s skills.

#### Q&A skill
This approach is more suitable for the case when you need your product to reply on some pre-defined users\' requests with some pre-defined replies.
Click on _Add questions and answers_ and then create a bunch of questions with appropriate answers to teach your project for new voice skill.

Zenbox provides a simple to use interface allowing you to add a question phrases and answers.
Then Zenbox will proceed a similar phrases with usage of machine learning algorithms.

{% include note.html text="Please note that the more samples are provided - the better the result can be expected." %}

## Pricing
Zenbox provides a fixed pricing strategy per activated unit.
The unit is a unique device that uses Zenbox API to process customers\' voice requests.

{% include note.html text="Thus Zenbox won't charge you for each voice request. The price will be fixed per unit independently from requests count." %}

Each Zenbox voice skill has a price per unit and Zenbox charges the total price once a new unique unit start to send voice requests to Zenbox API.
If you enable some additional skills further, Zenbox will charge the difference between the old price and new one from each returned unit once it 
send any request again.

{% include note.html text="Zenbox won't charge idle units if they don't send any requests." %}

You can see the total amount of upcoming payment on the _Overview_ page of you project Dashboard.

## Project settings
If you click the cog icon in the top right corner of the project\'s Dashboard you will be forwarded to the project settings page.
Here you can obtain you project API key to integrate the voice capabilities into your product, change the project\'s name and manage the users 
who have an access to this project.

### Users management
To grant any third-party user with an access to manage skills and view project usage statistics, just click on _Grant Access_ button and type an email 
of that user.

{% include note.html text="Note that this email should be linked to the Facebook or Github account of this user." %}

Such user won\'t be granted to change project\'s name or delete this project.

## Usage statistics
Zenbox provides an overall usage statistics for you project for any arbitrary period of time.
It contains a total price, the count of requests and units, and popularity of each voice skill.

{% include note.html text="This statistics is not personalised." %}

To see a statistics just click on _Statistics_ link on the navigation bar.
Then select an appropriate period of time if needed.

## Integrate Zenbox into your product
Once you have tested your Zenbox project, it\'s a time to integrate it into your real devices and applications.
To do this your developers have to use Zenbox SDK or Zenbox HTTP API described in the _Developers Guide_.
All you need for that - is to provide them an API key of your Zenbox project from _Settings_ page or grant them an access to the project.

<div class="text-center padding-top-2x">
<a href="/developers/" class="btn btn-outlined btn-default">Go to Developers Guide</a>
</div>