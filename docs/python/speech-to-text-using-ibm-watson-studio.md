# 使用 IBM Watson Studio 将语音转换为文本

> 原文:[https://www . geesforgeks . org/speech-to-text-use-IBM-Watson-studio/](https://www.geeksforgeeks.org/speech-to-text-using-ibm-watson-studio/)

**IBM Watson Studio** 是一个**集成环境**，旨在开发、培训、管理模型和部署人工智能驱动的应用程序，是一个在 IBM Cloud 上交付的**软件即服务(SaaS)** 解决方案。IBM 云提供了许多**服务**，如语音到文本、文本到语音、视觉识别、自然语言分类器、语言翻译器等。

语音转文本服务将音频转换为文本，以实现应用程序的语音转换功能。

#### 创建服务的实例

1.  转到 IBM 云目录中的[语音转文本](https://cloud.ibm.com/catalog/services/speech-to-text)页面。
2.  注册一个免费的 IBM Cloud 帐户或登录。
3.  点击**创建**。

#### 将要验证的凭据复制到您的服务实例

1.  从 [IBM 云资源列表](https://cloud.ibm.com/resources)中，单击您的语音转文本服务实例，转到语音转文本服务仪表板页面。
2.  在**管理**页面，点击**显示凭证**查看您的凭证。
3.  复制 **API 键**和 **URL** 值。

**所需模块:**

1.  JSON
2.  **ibm_watson:** 这个模块没有预定义 Python。要安装它，请在终端中键入以下命令。

    ```py
    pip install ibm_watson

    ```

现在，您已经准备好使用 IBM 云服务了。

**下面的代码说明了使用 Python 和 web socket 接口使用 IBM Watson studio 的语音转文本服务**

```py
#Python Program To Use IBM Watson
# Studio's Speech To Text Below Code
# Accepts only .mp3 Format of Audio
# File 

import json
from os.path import join, dirname
from ibm_watson import SpeechToTextV1
from ibm_watson.websocket import RecognizeCallback, AudioSource
from ibm_cloud_sdk_core.authenticators import IAMAuthenticator

# Insert API Key in place of 
# 'YOUR UNIQUE API KEY'
authenticator = IAMAuthenticator('YOUR UNIQUE API KEY') 
service = SpeechToTextV1(authenticator = authenticator)

#Insert URL in place of 'API_URL' 
service.set_service_url('API_URL')

# Insert local mp3 file path in
# place of 'LOCAL FILE PATH' 
with open(join(dirname('__file__'), r'LOCAL FILE PATH'), 
          'rb') as audio_file:

        dic = json.loads(
                json.dumps(
                    service.recognize(
                        audio=audio_file,
                        content_type='audio/flac',   
                        model='en-US_NarrowbandModel',
                    continuous=True).get_result(), indent=2))

# Stores the transcribed text
str = ""

while bool(dic.get('results')):
    str = dic.get('results').pop().get('alternatives').pop().get('transcript')+str[:]

print(str)
```

**输出**

```py
The Output will be Transcript (Text) of audio file.

```