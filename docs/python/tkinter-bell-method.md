# Tkinter–bell()方法

> 原文:[https://www.geeksforgeeks.org/tkinter-bell-method/](https://www.geeksforgeeks.org/tkinter-bell-method/)

**先决条件:** [Python 图形用户界面–tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/)

Python 为开发图形用户界面提供了多个选项。在所有的 GUI 方法中， *tkinter* 是最常用的方法。它是 Python 附带的 Tk 图形用户界面工具包的标准 Python 接口。Python 与 *tkinter* 是创建图形用户界面应用程序最快最简单的方法。使用 *tkinter* 创建一个图形用户界面是一个简单的任务。

在本文中，我们将学习 *Tkinter* 中的*铃()*方法。

这个方法在窗口的显示屏上响铃并返回一个空字符串。 *Tkinter 铃声()*是操作系统的默认声音，要在 *Tkinter* 应用中更改铃声声音，需要得到系统声音设置并需要更改默认声音。

**语法:**

```py
Object_name.bell()
```

**实施:**

## 蟒蛇 3

```py
# Import module
from tkinter import *

# Create object
root = Tk()

# Adjust size
root.geometry("400x400")

# Bell function
def bell():
    # call bell method
    root.bell()

# Add button
Button(root,text="Bell",command=bell).pack()

# Execute tkinter
root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-522940-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201204214720/What-is-Bell-in-Tkinter.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201204214720/What-is-Bell-in-Tkinter.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201204214720/What-is-Bell-in-Tkinter.mp4)</video>