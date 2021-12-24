# 用 Python 说出单词的意思

> 原文:[https://www . geesforgeks . org/speak-the-词义-use-python/](https://www.geeksforgeeks.org/speak-the-meaning-of-the-word-using-python/)

下面的文章展示了如何通过使用两个名为 [pyttsx3](https://www.geeksforgeeks.org/python-text-to-speech-by-using-pyttsx3/#:~:text=pyttsx3%20is%20a%20text%2Dto,a%20reference%20to%20a%20pyttsx3.) 和 [PyDictionary](https://www.geeksforgeeks.org/pydictionary-module-in-python/) 的模块，让我们的系统说出作为输入给出的单词的含义。当我们想知道某个词的意思时，是模块说出了意思。

### 需要的模块

*   **PyDictionary:** 它是 Python 2-3 获取单词的含义、翻译、同义词和反义词的词典模块。它使用 WordNet 来实现它的功能，并且依赖于名为 Requests、BeautifulSoup4 和 goslate 的模块。
*   **pyttsx3:** 是一个文本到语音库。这个模块为我们的系统提供了声音，以便他们可以与我们交流。Pyttsx3 在 windows 中使用 sapi5，在 windows 中使用 espeak。

两个模块都可以通过使用 pip 以下列方式安装:

```py
pip install PyDictionary
pip install pyttsx3  
```

### 工作

如上所述，通过两个模块的组合，我们将生成所需的功能，并为此采取了以下步骤:

*   定义了一种方法，使系统搜索作为输入提供的单词的含义
*   另一种方法是让系统大声说出与所提供的输入相对应的输出。
*   这里返回的输出可能是一个字典，所以我们必须提取提供的单词的每个含义，因为它将是键值格式。

下面是实现。

## 蟒蛇 3

```py
import pyttsx3
from PyDictionary import PyDictionary

class Speaking:

    def speak(self, audio):

        # Having the initial constructor of pyttsx3
        # and having the sapi5 in it as a parameter
        engine = pyttsx3.init('sapi5')

        # Calling the getter and setter of pyttsx3
        voices = engine.getProperty('voices')

        # Method for the speaking of the the assistant
        engine.setProperty('voice', voices[0].id)
        engine.say(audio)
        engine.runAndWait()

class GFG:
    def Dictionary(self):
        speak = Speaking()
        dic = PyDictionary()
        speak.speak("Which word do u want to find the meaning sir")

        # Taking the string input
        query = str(input())
        word = dic.meaning(query)
        print(len(word))

        for state in word:
            print(word[state])
            speak.speak("the meaning  is" + str(word[state]))

if __name__ == '__main__':
    GFG()
    GFG.Dictionary(self=None)
```

**输出:**

<video class="wp-video-shortcode" id="video-504955-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201023212141/Meaning.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201023212141/Meaning.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201023212141/Meaning.mp4)</video>