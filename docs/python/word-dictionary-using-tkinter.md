# 使用 Tkinter 的单词词典

> 原文:[https://www . geesforgeks . org/word-dictionary-using-tkinter/](https://www.geeksforgeeks.org/word-dictionary-using-tkinter/)

**先决条件:**

*   [**【tkinter】**](https://www.geeksforgeeks.org/transparent-window-in-tkinter/)
*   [**【皮词典】**](https://www.geeksforgeeks.org/pydictionary-module-in-python/)

Python 为开发图形用户界面提供了多个选项。在所有的 GUI 方法中，tkinter 是最常用的方法。它是 Python 附带的 Tk 图形用户界面工具包的标准 Python 接口。

在这篇文章中，我们将学习如何在 Tkinter 中制作单词词典。

**PyDictionary** 是 Python2 和 Python3 的词典(如英语词典中)模块。PyDictionary 为一个单词提供以下服务:

*   含义
*   翻译
*   同义词
*   反义词

### 方法

*   导入模块
*   创建正常 Tkinter 窗口
*   添加一些按钮、标签和框架

**语法:**

> **#按钮**
> 
> 按钮(对象名称，文本=“输入文本”，* *属性)
> 
> 标签
> 
> 标签(对象名称，文本=“输入文本”，命令=“输入命令”，* *属性)
> 
> **#车架**
> 
> 框架(对象名称，* *属性)

*   创建一个名为**的函数。这个功能会给出给定单词的意思、同义词&反义词。**
*   执行代码

**程序:**

## 蟒蛇 3

```
# Import Required Library
from tkinter import *
from PyDictionary import PyDictionary

# Create Objects
dictionary = PyDictionary()
root = Tk()

# Set geometry
root.geometry("400x400")

def dict():
    meaning.config(text=dictionary.meaning(word.get())['Noun'][0])
    synonym.config(text=dictionary.synonym(word.get()))
    antonym.config(text=dictionary.antonym(word.get()))

# Add Labels, Button and Frames
Label(root, text="Dictionary", font=(
    "Helvetica 20 bold"), fg="Green").pack(pady=10)

# Frame 1
frame = Frame(root)
Label(frame, text="Type Word", font=("Helvetica 15 bold")).pack(side=LEFT)
word = Entry(frame, font=("Helvetica 15 bold"))
word.pack()
frame.pack(pady=10)

# Frame 2
frame1 = Frame(root)
Label(frame1, text="Meaning:- ", font=("Helvetica 10 bold")).pack(side=LEFT)
meaning = Label(frame1, text="", font=("Helvetica 10"))
meaning.pack()
frame1.pack(pady=10)

# Frame 3
frame2 = Frame(root)
Label(frame2, text="Synonym:- ", font=("Helvetica 10 bold")).pack(side=LEFT)
synonym = Label(frame2, text="", font=("Helvetica 10"))
synonym.pack()
frame2.pack(pady=10)

# Frame 4
frame3 = Frame(root)
Label(frame3, text="Antonym:- ", font=("Helvetica 10 bold")).pack(side=LEFT)
antonym = Label(frame3, text="", font=("Helvetica 10"))
antonym.pack(side=LEFT)
frame3.pack(pady=10)

Button(root, text="Submit", font=("Helvetica 15 bold"), command=dict).pack()

# Execute Tkinter
root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-539039-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210108102207/FreeOnlineScreenRecorderProject9.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210108102207/FreeOnlineScreenRecorderProject9.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210108102207/FreeOnlineScreenRecorderProject9.mp4)</video>