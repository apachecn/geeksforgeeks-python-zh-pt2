# 使用 Python Tkinter 的维基百科摘要生成器

> 原文:[https://www . geesforgeks . org/Wikipedia-summary-generator-use-python-tkinter/](https://www.geeksforgeeks.org/wikipedia-summary-generator-using-python-tkinter/)

**先决条件:**

*   tkinter
*   [维基百科](https://www.geeksforgeeks.org/wikipedia-module-in-python/)

Python 为开发图形用户界面提供了多种选择。在所有的 GUI 方法中，Tkinter 是最常用的方法。Python 搭配 Tkinter 输出了创建 GUI 应用程序最快最简单的方法。

**维基百科**是一个 Python 库，可以方便地从“wikipedia.org”中访问和解析数据。这里，我们使用这个模块的 summary 函数来获取给程序的参数(字符串)的摘要。

### 装置

要安装维基百科库，只需在终端输入:

> pip 安装维基百科

### 方法

*   导入模块
*   创建普通窗口
*   添加按钮
*   创建从维基百科中删除摘要的机制
*   显示摘要
*   执行代码

**程序:**

## 蟒蛇 3

```
from tkinter import Tk, Frame, Toplevel, Entry, Button, Text, Scrollbar, END, INSERT
from tkinter.messagebox import showerror
from wikipedia import summary

# create function which will show summary
def get_summary():

    # if summary will be fetch from internet
    try:

        # clear text area
        answer.delete(1.0, END)

        # show summary in text area
        answer.insert(INSERT, summary(keyword_entry.get()))

    # if any it will give error, it will be shown in a new error window
    except Exception as error:

      # Title of new error window is "Error" and message will be
      # string given in variable error
        showerror("Error", error)

# create a GUI window
root = Tk()

# set title of window
root.title("Wikipedia Summary")

# set geometry of geometry
root.geometry("770x650")

# set window's width and height to 
# false => window will not be resizable
root.resizable(False, False)

# set background colour of window
root.configure(bg="dark grey")

# create a frame for entry and button
top_frame = Frame(root, bg="dark grey")
top_frame.pack(side="top", fill="x", padx=50, pady=10)

# create a frame for text area where summary will be displayed
bottom_frame = Frame(root, bg="dark grey")
bottom_frame.pack(side="top", fill="x", padx=10, pady=10)

# create a entry box where user can enter a keyword
keyword_entry = Entry(top_frame, font=("Arial", 20, "bold"), width=25, bd=4)
keyword_entry.pack(side="left", ipady=6)

# create a search button
search_button = Button(top_frame, text="SEARCH", font=(
    "Arial", 18, "bold"), width=15, bd=4, command=get_summary)
search_button.pack(side="right")

# create a scroll bar for text area
scroll = Scrollbar(bottom_frame)

# create a text area where summary will be displayed
answer = Text(bottom_frame, font=("Arial", 18), fg="red",
              width=55, height=20, bd=5, yscrollcommand=scroll.set)
answer.pack(side="left", fill="y")
scroll.pack(side="left", fill="y")

# start the GUI
root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-544394-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210116105202/video.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210116105202/video.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210116105202/video.mp4)</video>