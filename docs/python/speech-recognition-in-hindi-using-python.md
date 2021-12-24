# 使用 Python 进行印地语语音识别

> 原文:[https://www . geesforgeks . org/使用 python 的印地语语音识别/](https://www.geeksforgeeks.org/speech-recognition-in-hindi-using-python/)

我们可以使用 Python 进行语音识别，它主要用于识别英语单词。然而，在本文中，我们将使用 Python，这样它也可以在语音识别模块的帮助下识别印地语单词。

#### 要求:

*   **语音识别模块:**它是一个库，借助于这个库 Python 可以识别给定的命令。我们必须使用画中画进行语音识别。

```
pip install SpeechRecognition

```

*   **PyAudio Module:** 它是一组针对 *PortAudio* 的 Python 绑定，这是一个与音频驱动接口的跨平台 C++库。我们还需要安装 *Pyaudio* ，因为语音识别模块依赖于它。

```
pip install PyAudio

```

如果上述命令在 windows 中不起作用，请在 windows 命令提示符下使用以下命令:

```
pip install pipwin
```

```
pipwin install pyaudio
```

我们将使用*谷歌语音识别 API* 让软件理解印地语。我们将把语言指定为 *hn-IN。*

**下面是完整的 Python 程序，用于接收印地语输入命令并识别它们:**

## 蟒蛇 3

```
# import required module
import speech_recognition as sr

# explicit function to take input commands 
# and recognize them
def takeCommandHindi():

    r = sr.Recognizer()
    with sr.Microphone() as source:

        # seconds of non-speaking audio before 
        # a phrase is considered complete
        print('Listening')
        r.pause_threshold = 0.7  
        audio = r.listen(source)  
        try:
            print("Recognizing")
            Query = r.recognize_google(audio, language='hi-In')

            # for listening the command in indian english
            print("the query is printed='", Query, "'")

        # handling the exception, so that assistant can 
        # ask for telling again the command
        except Exception as e:
            print(e)  
            print("Say that again sir")
            return "None"
        return Query

# Driver Code

# call the function
takeCommandHindi()
```

**输出:**

<video class="wp-video-shortcode" id="video-512237-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201110162132/hindigfg.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201110162132/hindigfg.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201110162132/hindigfg.mp4)</video>