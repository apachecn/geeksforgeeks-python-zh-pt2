# Python 中使用 Tkinter 的文本到语音 GUI 转换器

> 原文:[https://www . geesforgeks . org/text-to-speech-GUI-converter-using-tkinter-in-python/](https://www.geeksforgeeks.org/text-to-speech-gui-convertor-using-tkinter-in-python/)

**先决条件:**[Tkinter 简介](https://www.geeksforgeeks.org/python-gui-tkinter/)

Tkinter 是 Python 的标准图形用户界面库。Python 与 tkinter 相结合，为创建图形用户界面应用程序提供了一种快速简单的方法。通过这个库，我们可以为用 Python 构建图形用户界面应用程序做出令人信服的选择，尤其是对于不需要现代光泽的应用程序，而首要任务是快速构建功能性和跨平台的东西。

**创建 tkinter 应用程序:**

> 1.  Import module–-tkinter
> 2.  Create the main window (container)
> 3.  Add any number of widgets to the main window.
> 4.  Apply event triggers to widgets.

现在，让我们创建一个基于图形用户界面的文本到语音转换器应用程序，将文本转换成语音。

python 中有很多库，其中之一是 gTTS(谷歌文本到语音)，这是一个 Python 库和 CLI 工具，用于与谷歌翻译的文本到语音 API 接口。

要安装 **gTTS** ，只需进入您的终端并键入:

```
pip install gTTS
```

下面是实现:

## 蟒蛇 3

```
# importing required module
from tkinter import *
from gtts import gTTS

# this module helps to
# play the converted audio 
import os

# create tkinter window
root = Tk()

# styling the frame which helps to 
# make our background stylish
frame1 = Frame(root,
               bg = "lightPink",
               height = "150")

# place the widget in gui window
frame1.pack(fill = X)

frame2 = Frame(root,
               bg = "lightgreen",
               height = "750")
frame2.pack(fill=X)

# styling the label which show the text 
# in our tkinter window
label = Label(frame1, text = "Text to Speech",
              font = "bold, 30",
              bg = "lightpink")

label.place(x = 180, y = 70)

# entry is used to enter the text 
entry = Entry(frame2, width = 45,
              bd = 4, font = 14)

entry.place(x = 130, y = 52)
entry.insert(0, "")

# define a function which can
# get text and convert into audio
def play():

    # Language in which you want to convert 
    language = "en"

   # Passing the text  and language, 
   # here we have  slow=False. Which tells 
   # the module that the converted audio should 
   # have a high speed 

    myobj = gTTS(text = entry.get(),
                lang = language,
                slow = False)

    # give the name as you want to 
    # save the audio
    myobj.save("convert.wav")
    os.system("convert.wav")

# cereate a button which holds
# our play function using command = play
btn = Button(frame2, text = "SUBMIT",
             width = "15", pady = 10,
             font = "bold, 15",
             command = play, bg='yellow')

btn.place(x = 250,
          y = 130)

# give a title 
root.title("text_to_speech_convertor")

# we can not change the size
# if you want you can change
root.geometry("650x550+350+200")

# start the gui
root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-457732-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200721141554/textToSpeech_Trim.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200721141554/textToSpeech_Trim.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200721141554/textToSpeech_Trim.mp4)</video>