# Tkinter 中的 Python | pack()方法

> 原文:[https://www . geesforgeks . org/python-pack-method-in-tkinter/](https://www.geeksforgeeks.org/python-pack-method-in-tkinter/)

打包几何管理器在行或列中打包小部件。我们可以使用**填充**、**扩展**、**侧边**等选项来控制这个几何管理器。
与**网格**管理器相比，**包**管理器有些有限，但在少数但相当常见的情况下使用起来要容易得多:

*   将一个小部件放入一个框架(或任何其他容器小部件)中，并让它填充整个框架
*   将许多小部件放置在彼此之上
*   并排放置一些小部件

**代码#1:** 在框架内放置一个小部件，填充整个框架。我们可以借助**扩展**和**填充**选项来做到这一点。

## 蟒蛇 3

```
# Importing tkinter module
from tkinter import * from tkinter.ttk import *

# creating Tk window
master = Tk()

# creating a Fra, e which can expand according
# to the size of the window
pane = Frame(master)
pane.pack(fill = BOTH, expand = True)

# button widgets which can also expand and fill
# in the parent widget entirely
# Button 1
b1 = Button(pane, text = "Click me !")
b1.pack(fill = BOTH, expand = True)

# Button 2
b2 = Button(pane, text = "Click me too")
b2.pack(fill = BOTH, expand = True)

# Execute Tkinter
master.mainloop()
```