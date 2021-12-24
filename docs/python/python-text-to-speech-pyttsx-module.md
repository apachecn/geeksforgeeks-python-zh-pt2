# Python 文本转语音| pyttsx 模块

> 原文:[https://www . geesforgeks . org/python-文本到语音-pyttsx-module/](https://www.geeksforgeeks.org/python-text-to-speech-pyttsx-module/)

**pyttsx** 是一个跨平台的文本到语音库，与平台无关。使用这个库进行文本到语音转换的主要优点是它可以脱机工作。然而， *pyttsx* 只支持 Python 2.x。因此，我们将看到 pyttsx3，它被修改为使用相同的代码在 Python 2.x 和 Python 3.x 上工作。

**使用该命令进行安装:**

```py
pip install pyttsx3
```

**用法–**
首先我们需要导入库，然后使用`init()`功能进行初始化。这个函数可能需要 2 个参数。
`init(driverName string, debug bool)`

*   **驱动程序名称:**【可用驱动程序名称】***Windows 上的 sapi5***|***MacOS 上的 nsss***
*   **调试:**启用或禁用调试输出

初始化后，我们将使用`say()`功能使程序朗读文本。此方法也可能需要 2 个参数。
T1】

*   **文字:**任何你想听的文字。
*   **名称:**为本次演讲设置名称。(可选)

最后，为了运行演讲，我们使用`runAndWait()`所有的`say()`文本都不会被说出，除非翻译遇到`runAndWait()`。

**代码#1:** 说文字

```py
# importing the pyttsx library
import pyttsx3

# initialisation
engine = pyttsx3.init()

# testing
engine.say("My first code on text-to-speech")
engine.say("Thank you, Geeksforgeeks")
engine.runAndWait()
```

**代码#2:** 监听事件

```py
import pyttsx3

def onStart():
   print('starting')

def onWord(name, location, length):
   print('word', name, location, length)

def onEnd(name, completed):
   print('finishing', name, completed)

engine = pyttsx3.init()

engine.connect('started-utterance', onStart)
engine.connect('started-word', onWord)
engine.connect('finished-utterance', onEnd)

sen = 'Geeks for geeks is a computer portal for Geeks'

engine.say(sen)
engine.runAndWait()
```

**为什么是 pyttsx？**
它可以离线工作，不像其他文本到语音库。 *pyttsx* 没有将文本保存为音频文件，而是在那里说出来。这使得它更可靠地用于基于语音的项目。