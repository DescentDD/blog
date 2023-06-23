---
title: AzureTTS使用python代码
date: 2023-06-14 00:51:46
tags: 整活
---

## Azure介绍

是什么我不用多说吧

## 直接上代码，调用AzureTTS接口

```python
import os
import azure.cognitiveservices.speech as speechsdk

# 配置api
speech_config = speechsdk.SpeechConfig(subscription='SPEECH_KEY', region='SPEECH_REGION')
audio_config = speechsdk.audio.AudioOutputConfig(use_default_speaker=True)

# 语言选择
speech_config.speech_synthesis_voice_name='zh-CN-XiaoyiNeural'

speech_synthesizer = speechsdk.SpeechSynthesizer(speech_config=speech_config, audio_config=audio_config)
while(1):
    # 说话说话！
    print("说话说话！")
    text = input()
    speech_synthesis_result = speech_synthesizer.speak_text_async(text).get()
    print("说：{}".format(text))
   
```

## 有什么用捏？

可以拿来做语音助手或者老婆！
