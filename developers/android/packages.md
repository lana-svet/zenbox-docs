---
layout: page
title: Android SDK Packages
permalink: /developers/android/packages/
---

{% include header.html color="#94bf67" img="/img/android.png" title="Android SDK Packages" summary="The list of currently supported packages" %}

This list contains packages with `SpeechToText` and `TextToSpeech` implementations from different vendors.
You are free to choose any of them and include in your application depending on the plan of your Zenbox project and supported languages.

## Nuance SpeechKit
This package supports all Zenbox languages and provides `SpeechToText` and `TextToSpeech` services implementations.
To include Nuance Speechkit into your project, add this dependency in your `build.gradle` file

```groovy
compile 'com.justai.zenbox.android-sdk:nuance-speechkit:1.0.0'
```

To instantiate a Nuance SpeechKit in your app please use `NuanceSpeechToText` and `NuanceTextToSpeech` classes

```java
NuanceConfig config = new NuanceConfig(
                "Your Nuance app ID",
                "Your Nuance app name",
                "Your Nuance app key",
                "Nuance host", 443);
                
SpeechToText speechToText = new NuanceSpeechToText(this, Language.ENG_USA, config);
TextToSpeech textToSpeech = new NuanceTextToSpeech(this, Language.ENG_USA, config);
```

Before using this package you have to obtain your Nuance app credentials from [https://developer.nuance.com](https://developer.nuance.com) 
and provide them in `NuanceConfig`.

## Nuance voice trigger
This package supports all Zenbox languages and provides `VoiceTrigger` service implementation.
To include Nuance VoiceTrigger into your project, add these dependencies in your `build.gradle` file

```groovy
compile 'com.justai.zenbox.android-sdk:nuance-speechkit:1.0.0'
compile 'com.justai.zenbox.android-sdk:nuance-voicetrigger:1.0.0'
```

Nuance VoiceTrigger depends on the assets regarding the used language, thus you have to add one more dependency with these assets 
to make VoiceTrigger working.

`compile 'com.justai.zenbox.android-sdk:nuance-assets-en:1.0.0'` for English language  
`compile 'com.justai.zenbox.android-sdk:nuance-assets-ru:1.0.0'` for Russian language

To instantiate Nuance voice trigger use `NuanceVoiceTrigger` class

```java
VoiceTrigger voiceTrigger = new NuanceVoiceTrigger(this, Language.ENG_USA, Collections.singletonList("your trigger phrase"), NuanceVoiceTrigger.DEFAULT_THRESHOLD);
```

## Yandex SpeechKit
This package supports all Zenbox languages and provides `SpeechToText` and `TextToSpeech` services implementations.
To include Yandex Speechkit into your project, add this dependency in your `build.gradle` file

```groovy
compile 'com.justai.zenbox.android-sdk:yandex-speechkit:1.1.0'
```

To instantiate a Yandex SpeechKit in your app please use `YandexSpeechToText`, `YandexTextToSpeech` and `TandexVoiceTrigger` classes

```java
YandexSpeechToText speechToText = new YandexSpeechToText(this, "Your SpeechKit Mobile SDK key", YandexSpeechToText.LANG_EN);
YandexTextToSpeech textToSpeech = new YandexTextToSpeech(this, "Your SpeechKit Mobile SDK key", YandexTextToSpeech.LANG_EN, YandexTextToSpeech.VOICE_FEMALE_ALYSS);
YandexVoiceTrigger voiceTrigger = new YandexVoiceTrigger(this, "Your SpeechKit Mobile SDK key", "Your phrase spotter model data path");
```

Before using this package you have to obtain your SpeechKit Mobile SDK key from [https://tech.yandex.ru/speechkit/mobilesdk/](https://tech.yandex.ru/speechkit/mobilesdk/).

<div class="text-center padding-top-2x">
<a href="/developers/android/" class="btn btn-outlined btn-default">Back to Android SDK Guide</a>
</div>