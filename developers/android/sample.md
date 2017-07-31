---
layout: page
title: Android SDK Guide
permalink: /developers/android/sample/
---

{% include header.html color="#94bf67" img="/img/android.png" title="Android Sample" summary="This guide describes the usage of sample Android application" %}

We have prepared a sample Android app that uses Zenbox SDK to simplify the process of the introduction into the SDK API.
The spurce code of the sample application is placed on Github.

<div class="text-center">
<a href="https://github.com/just-ai/zenbox-android-sample" target="_blank" class="btn btn-default"><i class="fa fa-fw fa-github"></i> Fork on Github</a>
</div>

## How to start with sample app
Here is a short step-by-step guide about how to start building your voice enabled device or app with Zenbox.

### Create Zenbox project
First of all you have to create Zenbox project in [Zenbox Dashboard](https://sdk.zenbox.ai) and obtain your **project API key**.
You can find it on the setting page of your project.

### Enable skills
On the skills page of your project please enable some set of voice skills.
These skills will teach Zenbox to recognise user\'s voice requests and produce some appropriate results.

{% include note.html text="The sample app contains a simple Music skill implementation, so you can enable the Music skill to play with it." %}

### Obtain your API keys
You have also obtain an API key for Yandex SpeechKit to enable speech-to-text and text-to-speech components of sample app.
You can obtain your evaluation key on the [Yandex SpeechKit Mobile SDK page](https://tech.yandex.ru/speechkit/mobilesdk/)

### Clone and build a sample app
Clone the sample app from our Github repository and import it to any of your favorite IDE, like Android Studio.
Provide your Zenbox project API and Yandex SpeechKit API keys in the `MainActivity.java` file.

{% include note.html text="You can build and run the sample app without an IDE with <i>./gradlew :app:installDebug</i> command." %}

### Run the sample app
To run an app you can use any regular Android device with microphones and internet access.
Zenbox SDK is ready for OEM Android that is why **there are no requirements regarding any Google services** installed on the device.

{% include note.html text="The sample app uses GUI but the same code could be used even wuthout any GUI on any Android device." %}

After running the screen with prompt and microphone button appears.
Tap the button and start to speak right after the earcon audio signal.

Please note that you can speak anything regarding the enbaled skills on the Zenbox Dashboard.
Each skill provides a list of supported sentences.
Please refer to these lists to know what to say.

### Further steps
After playing with the sample app you can discover the source code finding more how Zenbox SDK is used to process the user\'s speech.

<div class="text-center padding-top-2x">
<a href="/developers/android/" class="btn btn-outlined btn-default">Back to Android SDK Guide</a>
</div>