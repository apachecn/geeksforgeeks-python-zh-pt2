# Python–wxPython 中的 Move()函数

> 原文:[https://www . geesforgeks . org/python-move-function-in-wxpython/](https://www.geeksforgeeks.org/python-move-function-in-wxpython/)

在这篇特别的文章中，我们将学习如何将我们的窗口移动到一个特定的点。这可以使用 wx 中的 Move()函数来实现。wxPython 的窗口类。
Move()使用 x 和 y 点将窗口移动到特定的 x、y 点。

> **语法:**
> 
> ```
> wx.Move(self, x, y, flags=SIZE_USE_EXISTING)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | x | （同 Internationalorganizations）国际组织 | 所需的 x 位置。 |
> | y | （同 Internationalorganizations）国际组织 | 所需的 y 位置。 |
> | 旗 | （同 Internationalorganizations）国际组织 | SetSize 的标志。 |

**代码示例#1:**

```
# import wxPython
import wx

# frame class
class MoveWindow(wx.Frame):

    def __init__(self, parent, title):
        super(MoveWindow, self).__init__(parent, title = title,
            size =(300, 200))
        # move window using Move() function
        self.Move((500, 250))

def  main():
    app = wx.App()
    move = MoveWindow(None, title ='Move()')
    move.Show()
    app.MainLoop()

if __name__ == '__main__':
    main()
```

**输出:**
![](img/04239f286e289a3d17b5ae41f6572fff.png)

**代码示例#2:**

```
# import wxPython
import wx

# frame class
class MoveWindow(wx.Frame):

    def __init__(self, parent, title):
        super(MoveWindow, self).__init__(parent, title = title,
            size =(300, 200))
        # move window to (900, 600) using Move() function
        self.Move((900, 600))

def  main():
    app = wx.App()
    move = MoveWindow(None, title ='Move()')
    move.Show()
    app.MainLoop()

if __name__ == '__main__':
    main()
```

**输出:**
![](img/390ec281a67f7b5047bab4bc37b8cb00.png)