# Tkit–悬停时改变其属性的按钮

> 原文:[https://www . geesforgeks . org/tkinter-button-the-changes-its-on-hover/](https://www.geeksforgeeks.org/tkinter-button-that-changes-its-properties-on-hover/)

Python 为开发图形用户界面提供了多个选项。在所有的 GUI 方法中， *tkinter* 是最常用的方法。它是 Python 附带的 Tk 图形用户界面工具包的标准 Python 接口。Python 与 *tkinter* 是创建图形用户界面应用程序最快最简单的方法。使用 *tkinter* 创建一个图形用户界面是一个简单的任务。

在本文中，我们将创建一个在悬停时更改其属性的按钮。

**分步方法:**

*   导入 *tkinter* 模块*。*

## 蟒蛇 3

```py
# import required module
from tkinter import *
```

*   创建通用功能，为每个按钮提供悬停时的更改功能。

*config()* 方法用于更改任何小部件的属性。注意在*配置()*方法中 *bg* 和*背景*是两个不同的选项，*背景*代表背景色。

**语法:**

```py
widget.config(**options)
```

下面是实现:

## 蟒蛇 3

```py
# function to change properties of button on hover
def changeOnHover(button, colorOnHover, colorOnLeave):

    # adjusting backgroung of the widget
    # background on entering widget
    button.bind("<Enter>", func=lambda e: button.config(
        background=colorOnHover))

    # background color on leving widget
    button.bind("<Leave>", func=lambda e: button.config(
        background=colorOnLeave))
```

*   在驱动程序代码中创建一个按钮，并调用显式函数。

## 蟒蛇 3

```py
# Driver Code
root = Tk()

# create button
# assign button text along
# with background color
myButton = Button(root,
                  text="On Hover - Background Change",
                  bg="yellow")
myButton.pack()

# call function with background
# colors as argument
changeOnHover(myButton, "red", "yellow")

root.mainloop()
```

**以下是基于上述方法的完整程序:**

## 蟒蛇 3

```py
# import required module
from tkinter import *

# function to change properties of button on hover
def changeOnHover(button, colorOnHover, colorOnLeave):

    # adjusting backgroung of the widget
    # background on entering widget
    button.bind("<Enter>", func=lambda e: button.config(
        background=colorOnHover))

    # background color on leving widget
    button.bind("<Leave>", func=lambda e: button.config(
        background=colorOnLeave))

# Driver Code
root = Tk()

# create button
# assign button text along
# with background color
myButton = Button(root,
                  text="On Hover - Background Change",
                  bg="yellow")
myButton.pack()

# call function with background
# colors as argument
changeOnHover(myButton, "red", "yellow")

root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-514582-1" width="665" height="374" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20201203194659/tkinter-button.webm?_=1">[https://media.geeksforgeeks.org/wp-content/cdn-uploads/20201203194659/tkinter-button.webm](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20201203194659/tkinter-button.webm)</video>