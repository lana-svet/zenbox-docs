---
layout: page
title: Android SDK Guide
permalink: /developers/android/
---

{% include header.html color="#94bf67" img="/img/android.png" title="Android SDK Guide" summary="This guide shows how to use Zenbox Android SDK in your application or device" %}

Zenbox Android SDK simplifies the usage of [HTTP API](/developers/http/) and also provides you a ready-to-use components for speech recognition and synthesis.
Also it contains an abstraction level to implement the voice skills capabilities that should be run on the device (like music or alarm skills).
This you do not have to implement everything on your own. Instead - you may just initialize Zenbox service properly and have a voice enabled application ready to work.

## About this guide
This guide provides you a step-by-step introduction into Zenbox Android SDK with comprehensive description of every aspect of API.
You have to be familiar with Android, Gradle and Java to continue.

## Sample application
Learning by sample maybe easier and much faster sometimes. 
That is why we have prepared a sample Android application that shows Zenbox SDK usage.
[Read this article](/developers/android/sample/) to learn more about the sample app.

## Zenbox Android SDK basics
Zenbox SDK combines speech-to-text, text-to-speech, voice triggers and NLP components in a single [ZenboxService](javadoc/com/justai/zenbox/sdk/ZenboxService.html) class 
that simplifies the work with Zenbox API and clues all these components together.

### JavaDocs
You can find all JavaDocs with detailed description of each Zenbox SDK component on [this page](javadoc/).

### Dependencies
To use Zenbox SDK you have to include SDK dependencies into your Android project\'s `build.gradle` file

```groovy
repositories {
    maven {
        url  "http://dl.bintray.com/just-ai/zenbox-android-sdk"
    }
}
dependencies {
    ...
    compile 'com.justai.zenbox:android-sdk:1.0.1'
}
```

### ZenboxService instantiation
[ZenboxService](javadoc/com/justai/zenbox/sdk/ZenboxService.html) should be instantiated only once in your application.
It can be destroyed and instantiated again if you need to release all resources (for example once your app invokes `onPause`).

To create a new instance of [ZenboxService](javadoc/com/justai/zenbox/sdk/ZenboxService.html) use [ZenboxService.Builder](javadoc/com/justai/zenbox/sdk/ZenboxService.Builder.html) class

```java
ZenboxService service = new ZenboxService.Builder(this, "Your Zenbox Project API key", "Unique Unit ID")
                .setSpeechToText(speechToText)
                .setTextToSpeech(textToSpeech)
                .build();
```

You have to provdie a [SpeechToText](javadoc/com/justai/zenbox/sdk/api/SpeechToText.html) and [TextToSpeech](javadoc/com/justai/zenbox/sdk/api/TextToSpeech.html) implementations regarding the service of your choice 
(e.g. Yandex SpeechKit or Nuance SpeechKit). 
These implementations are provided by Zenbox SDK already and can be found on [this page](/developers/android/packages/).
You have to include an appropriate dependencies into you `build.gradle` and instantiate them in your code.

For example to include the Yandex SpeechKit implementation of speech-to-text and text-to-speech components 
add the following into your `build.gradle`

```groovy
dependencies {
    ...
    compile 'com.justai.zenbox:android-sdk:1.0.0'
    compile 'com.justai.zenbox.android-sdk:yandex-speechkit:1.0.0'
}
```

In your code instantiate [ZenboxService](javadoc/com/justai/zenbox/sdk/ZenboxService.html)

```java
YandexSpeechToText speechToText = new YandexSpeechToText(this, SPEECH_KIT_KEY, YandexSpeechToText.LANG_EN);
YandexTextToSpeech textToSpeech = new YandexTextToSpeech(this, SPEECH_KIT_KEY, YandexTextToSpeech.LANG_EN, YandexTextToSpeech.VOICE_FEMALE_ALYSS);
ZenboxService service = new ZenboxService.Builder(this, "Your Zenbox Project API key", "Unique Unit ID")
                .setSpeechToText(speechToText)
                .setTextToSpeech(textToSpeech)
                .build();
```

## Supported packages
Please refer to [this page](/developers/android/packages) to learn more about supported [SpeechToText](javadoc/com/justai/zenbox/sdk/api/SpeechToText.html), [TextToSpeech](javadoc/com/justai/zenbox/sdk/api/TextToSpeech.html) and [VoiceTrigger](javadoc/com/justai/zenbox/sdk/api/VoiceTrigger.html) implementations.
You are free to use any of them depending on your Zenbox project plan.

## Start listening
To start recognition of the user\'s speech request, use [ZenboxService.startRecognition()](javadoc/com/justai/zenbox/sdk/ZenboxService.html#startRecognition) method.
It will do the required actions and start the recognition through the provided [SpeechToText](javadoc/com/justai/zenbox/sdk/api/SpeechToText.html) implementation.

## ZenboxService lifecycle
During the application lifecycle [ZenboxService](javadoc/com/justai/zenbox/sdk/ZenboxService.html) changes it\'s internal state invoking required components to process the user\'s requests.
To handle [ZenboxService](javadoc/com/justai/zenbox/sdk/ZenboxService.html) lifecycle callbacks please provide your [ZenboxListener](javadoc/com/justai/zenbox/sdk/listener/ZenboxListener.html) interface implementation

```java
ZenboxService service = new ZenboxService.Builder(this, "Your Zenbox Project API key", "Unique Unit ID")
                .setSpeechToText(speechToText)
                .setTextToSpeech(textToSpeech)
                .setListener(new ZenboxListener() {
                                     @Override
                                     public void onTriggered() {
                                     }
                             
                                     @Override
                                     public void onStateChanged(State state) {
                                     }
                             
                                     @Override
                                     public void onRequest(RequestData data) {
                                     }
                             
                                     @Override
                                     public void onResponse(ResponseData response) {
                                     }
                                 })
                .build();
```

### ZenboxService lifecycle steps
The general lifecycle contains several steps.

When your code or [VoiceTrigger](javadoc/com/justai/zenbox/sdk/api/VoiceTrigger.html) component calls the [ZenboxService.startRecognition()](javadoc/com/justai/zenbox/sdk/ZenboxService.html#startRecognition--) method, ZenboxService stops all currently active 
processes (like text-to-speech synthesise or current request processing) and invokes a [ZenboxListener.onTriggered](javadoc/com/justai/zenbox/sdk/listener/ZenboxListener.html#onTriggered) method.
The background thread is used in this case and you are free to perform any desired actions in this method implementation.
ZenboxService waits until all actions are performed and starts a speech recognition process through the provided [SpeechToText](javadoc/com/justai/zenbox/sdk/api/SpeechToText.html) component.
The current state is changed to [State.LISTENING](javadoc/com/justai/zenbox/sdk/State.html#LISTENING) and [ZenboxListener.onStateChanged](http://localhost:4000/developers/android/javadoc/com/justai/zenbox/sdk/listener/ZenboxListener.html#onStateChanged-com.justai.zenbox.sdk.State-) is invoked on the main thread.

After a speech was recognised, ZenboxService goes to [State.PROCESSING](javadoc/com/justai/zenbox/sdk/State.html#PROCESSING) state and constructs a new [RequestData](javadoc/com/justai/zenbox/sdk/RequestData.html) instance with recognised 
user\'s query. Then the [ZenboxListener.onRequest(RequestData)](javadoc/com/justai/zenbox/sdk/listener/ZenboxListener.html#onRequest-com.justai.zenbox.sdk.RequestData-) method is invoked.
You can fulfill the RequestData with additional request parameters in this method implementation to pass additional content to Zenbox.

{% include note.html text="onRequest method is invoked on the background thread, thus you can perform any blocking operations during the RequestData fulfillment (e.g. database querying, filesystem operations an so on)." %}

This step is necessary because some voice skills require additional parameters to be passed with request.
Please learn more about each skill requirements on [this page](/skills/).

{% include note.html text="Each implementation of AbstractSkill added to ZenboxService will be invoked at this moment. Read below about Local skills below." %}

After a fulfillment, ZenboxService processes RequestData through the set of currently enabled voice skills in your Zenbox project on zenbox.ai.
Once the result is fetched ZenboxService synthesises the response speech and invokes [ZenboxListener.onResponse(ResponseData)](javadoc/com/justai/zenbox/sdk/listener/ZenboxListener.html#onResponse-com.justai.zenbox.sdk.ResponseData-) callback method.
During the speech synthesise ZenboxService stays in the [State.SPEAKING](javadoc/com/justai/zenbox/sdk/State.html#SPEAKING) state.

[ResponseData](javadoc/com/justai/zenbox/sdk/ResponseData.html) is an abstract class with possible [SuccessResponse](javadoc/com/justai/zenbox/sdk/ResponseData.SuccessResponse.html), [EmptyResponse](javadoc/com/justai/zenbox/sdk/ResponseData.EmptyResponse.html) or [ErrorResponse](javadoc/com/justai/zenbox/sdk/ResponseData.ErrorResponse.html) sub-classes.
Regarding to the type of ResponseData you can make a decision about the next steps in your application logic.

{% include note.html text="Please refer to the JavaDoc to learn more about fields in these classes." %}

If Zenbox requires some conversation with the user in response, ZenboxService automatically starts to listen again right after the speech synthesise.

### More lifecycle callbacks
If you need to control a lifecycle of each component of ZenboxService, you can add your listeners to each of [SpeechToText](javadoc/com/justai/zenbox/sdk/api/SpeechToText.html), [TextToSpeech](javadoc/com/justai/zenbox/sdk/api/TextToSpeech.html) and [VoiceTrigger](javadoc/com/justai/zenbox/sdk/api/VoiceTrigger.html) instances.
These listeners contain callback methods that signal the state changes of each component during the user\'s request processing.
For example

```java
textToSpeech.addListener(new TextToSpeechListener() {
                                 @Override
                                 public void onUtteranceStart(Utterance utterance) {
                                     mAnswerTextView.setText(utterance.getSpeech());
                                 }
                         
                                 @Override
                                 public void onUtteranceComplete(Utterance utterance) {
                                 }
                             });
```

## Local skills (AbstractSkill)
Some skills require to perform some actions locally on the device.
For example the music skill has to control a playback of the track list provided by Zenbox API.
Thus the developer has to implement a local skill logic depending on the platform.

There is a special [AbstractSkill](javadoc/com/justai/zenbox/sdk/api/AbstractSkill.html) class that should be extended by your implementation of each local skill.
This class already implements a [ZenboxListener](javadoc/com/justai/zenbox/sdk/listener/ZenboxListener.html) interface, thus ZenboxService calls it\'s
lifecycle callback methods automatically.

An AbstractSkill should implement [AbstractSkill.isActionSupported](javadoc/com/justai/zenbox/sdk/api/AbstractSkill.html#isActionSupported-java.lang.String-) 
returning `true` if the action of [ResponseData.SuccessResponse](javadoc/com/justai/zenbox/sdk/ResponseData.SuccessResponse.html) is supported 
by this particular implementation. Only if this method returns `true` the [AbstractSkill.onResponse](javadoc/com/justai/zenbox/sdk/api/AbstractSkill.html#onResponse-com.justai.zenbox.sdk.ResponseData.SuccessResponse-)
will be invoked with corresponding Zenbox response data.

This allows to clarify the logic handling only those responses the skill was implemented for.

### Add local skill
Each AbstractSkill implementation should be added to ZenboxService on the building step through a [ZenboxService.Builder.addSkill](javadoc/com/justai/zenbox/sdk/ZenboxService.Builder.html#addSkill-com.justai.zenbox.sdk.api.AbstractSkill-)
method. For example

```java
mZenboxService = new ZenboxService.Builder(this, mZenboxApiKey, mUnitId)
                .setListener(mZenboxListener)
                .setSpeechToText(speechToText)
                .setTextToSpeech(textToSpeech)
                .addSkill(new MusicSkill(textToSpeech))
                .build();
```

Please [refer to the sample app](sample) to see the sample `MusicSkill` implementation.

## Standby mode
Once you have constructed a [ZenboxService](javadoc/com/justai/zenbox/sdk/ZenboxService.html) instance, you should invoke [ZenboxService.invoke()](javadoc/com/justai/zenbox/sdk/ZenboxService.html#standby--) method 
to put ZenboxService into [State.STANDBY](javadoc/com/justai/zenbox/sdk/State.html#STANDBY) state.
This state terminates all current processes and automatically starts the [VoiceTrigger](javadoc/com/justai/zenbox/sdk/api/VoiceTrigger.html) if present.
Thus you can invoke this method each time you need to terminate ZenboxService in any state.

## Earcon signal
When performing speech recognition, it is important to indicate to the users that you are listening and that they are being heard.
[ZenboxService.Builder](javadoc/com/justai/zenbox/sdk/ZenboxService.Builder.html) provides you a [method](javadoc/com/justai/zenbox/sdk/ZenboxService.Builder.html#setEarcon-int-) to set your audio signal been played once the user initiates 
a new request. This method accepts an audio resource ID from the `raw` folder of your application and ZenboxService plays it automatically right 
before the start of speech recognition.

<div class="text-center padding-top-2x">
  <a href="http://sdk.zenbox.ai" target="_blank" class="btn btn-lg btn-primary">Create a Zenbox project now</a>
</div>