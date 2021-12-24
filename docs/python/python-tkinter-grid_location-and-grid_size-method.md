# Python Tkinter | grid_location()和 grid_size()方法

> 原文:[https://www . geesforgeks . org/python-tkinter-grid _ location-and-grid _ size-method/](https://www.geeksforgeeks.org/python-tkinter-grid_location-and-grid_size-method/)

Tkinter 用于开发图形用户界面应用程序。它支持各种小部件以及各种小部件方法或通用小部件方法。

## grid_location()方法–

此方法返回包含任何指定小部件(列、行)的元组。因为这个方法是一个小部件方法，你不能把它和主对象(或者 Tk()对象)一起使用。为了使用此方法，您应该首先创建一个框架，并将其视为父框架(或主框架)。

> **语法:** widget.grid_location(x，y)
> **参数:**
> **x** 和 **y** 是相对于 widget(父 widget)左上角的位置。

在下面的示例中，grid_location()用于获取小部件在 Frame 小部件中的位置。

## 蟒蛇 3

```
# This imports all functions in tkinter module
from tkinter import * from tkinter.ttk import *

# creating master window
master = Tk()

# This method is used to get the position
# of the desired widget available in any
# other widget
def click(event):

    # Here retrieving the size of the parent
    # widget relative to master widget
    x = event.x_root - f.winfo_rootx()
    y = event.y_root - f.winfo_rooty()

    # Here grid_location() method is used to
    # retrieve the relative position on the
    # parent widget
    z = f.grid_location(x, y)

    # printing position
    print(z)

# Frame widget, wil work as
# parent for buttons widget
f = Frame(master)
f.pack()

# Button widgets
b = Button(f, text = "Button")
b.grid(row = 2, column = 3)

c = Button(f, text = "Button2")
c.grid(row = 1, column = 0)

# Here binding click method with mouse
master.bind("<Button-1>", click)

# infinite loop
mainloop()
```

<video class="wp-video-shortcode" id="video-317076-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20190626010302/ice_video_20190626-005104_edit_0.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20190626010302/ice_video_20190626-005104_edit_0.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20190626010302/ice_video_20190626-005104_edit_0.mp4)</video>

## grid_size()方法–

此方法用于获取任何父小部件中存在的网格总数。这是一个小部件方法，因此不能与 master 对象一起使用。必须创建一个框架部件。

> **语法:**(列，行)= widget.grid_size()
> **返回值:**返回列和行(网格)的总数。

下面是 Python 代码-

## 蟒蛇 3

```
# This imports all functions in tkinter module
from tkinter import * from tkinter.ttk import *

# creating master window
master = Tk()

# This method is used to get the size
# of the desired widget i.e number of grids
# available in the widget
def grids(event):

    # Here, grid_size() method is used to get
    # the total number grids available in frame
    # widget
    x = f.grid_size()

    # printing (columns, rows)
    print(x)

# Frame widget, will work as
# parent for buttons widget
f = Frame(master)
f.pack()

# Button widgets
b = Button(f, text = "Button")
b.grid(row = 1, column = 2)

c = Button(f, text = "Button2")
c.grid(row = 1, column = 0)

# Here binding click method with mouse
master.bind("<Button-1>", grids)

# infinite loop
mainloop()
```

**输出:**
每次你点击鼠标按钮，它都会返回相同的值，直到没有添加更多的小部件或者行数和列数没有增加。

```
(3, 2)
```