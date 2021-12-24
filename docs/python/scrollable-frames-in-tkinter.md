# Tkinter 中的可滚动帧

> 原文:[https://www.geeksforgeeks.org/scrollable-frames-in-tkinter/](https://www.geeksforgeeks.org/scrollable-frames-in-tkinter/)

滚动条是一个小部件，用于滚动另一个小部件中的文本。例如，文本、画布框或列表框中的文本可以使用滚动条从上到下或从左到右滚动。滚动条有两种类型。它们是水平的和垂直的。水平滚动条对于从左到右查看文本非常有用。垂直滚动条用于从上到下滚动文本。
现在让我们看看如何创建滚动条。要创建滚动条，我们必须创建一个滚动条类对象，如下所示:

```py
h = Scrollbar(root, orient='horizontal')
```

这里 h 代表作为根窗口的子窗口创建的 scrollbar 对象。这里，方向表示水平滚动条的*水平*，垂直*表示垂直滚动条。类似地，为了创建垂直滚动条，我们可以编写:*

```py
v = Scrollbar(root, orient='vertical')
```

将滚动条附加到文本框、列表框等小部件后，我们必须为水平滚动条添加命令 *xview* ，为垂直滚动条添加 *yview* 。

```py
h.config(command=t.xview) #for horizontal scrollbar
v.config(command=t.yview) #for vertical scrollbar
```

现在让我们看一下将垂直和水平滚动条附加到文本小部件的代码。

## 蟒蛇 3

```py
# Python Program to make a scrollable frame
# using Tkinter

from tkinter import *

class ScrollBar:

    # constructor
    def __init__(self):

        # create root window
        root = Tk()

        # create a horizontal scrollbar by
        # setting orient to horizontal
        h = Scrollbar(root, orient = 'horizontal')

        # attach Scrollbar to root window at
        # the bootom
        h.pack(side = BOTTOM, fill = X)

        # create a vertical scrollbar-no need
        # to write orient as it is by
        # default vertical
        v = Scrollbar(root)

        # attach Scrollbar to root window on
        # the side
        v.pack(side = RIGHT, fill = Y)

        # create a Text widget with 15 chars
        # width and 15 lines height
        # here xscrollcomannd is used to attach Text
        # widget to the horizontal scrollbar
        # here yscrollcomannd is used to attach Text
        # widget to the vertical scrollbar
        t = Text(root, width = 15, height = 15, wrap = NONE,
                 xscrollcommand = h.set,
                 yscrollcommand = v.set)

        # insert some text into the text widget
        for i in range(20):
            t.insert(END,"this is some text\n")

        # attach Text widget to root window at top
        t.pack(side=TOP, fill=X)

        # here command represents the method to
        # be executed xview is executed on
        # object 't' Here t may represent any
        # widget
        h.config(command=t.xview)

        # here command represents the method to
        # be executed yview is executed on
        # object 't' Here t may represent any
        # widget
        v.config(command=t.yview)

        # the root window handles the mouse
        # click event
        root.mainloop()

# create an object to Scrollbar class
s = ScrollBar()

```

**输出:**

<video class="wp-video-shortcode" id="video-399666-1" width="640" height="360" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/uploads/20200420181829/Scrollable-frames-tkinter.webm?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200420181829/Scrollable-frames-tkinter.webm](https://media.geeksforgeeks.org/wp-content/uploads/20200420181829/Scrollable-frames-tkinter.webm)</video>