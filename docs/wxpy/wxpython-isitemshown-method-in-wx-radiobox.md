# wx xpython–wx 中的 IsItemShown()方法。无线电盒

> 原文:[https://www . geesforgeks . org/wxpython-isitemshow-method-in-wx-radio box/](https://www.geeksforgeeks.org/wxpython-isitemshown-method-in-wx-radiobox/)

在本文中，我们将学习与 wx 相关的`IsItemShown()`函数。wxPython 的 RadioBOx 类。IsItemShown()方法仅用于在当前显示项目时返回 True，或者在使用 Show 隐藏项目时返回 False。

请注意，对于未隐藏的项目，即使当前未显示整个 radiobox，该函数也会返回 True。

> **语法:**
> wx。收音机盒。IsItemShown(自我，n)
> 
> **参数**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | n | （同 Internationalorganizations）国际组织 | 从零开始的按钮位置。 |
> 
> **返回类型:** bool

**代码示例:**

```
import wx

class FrameUI(wx.Frame):

    def __init__(self, parent, title):
        super(FrameUI, self).__init__(parent, title = title, size =(300, 200))

        # function for in-frame components
        self.InitUI()

    def InitUI(self):
        # parent panel for radio box
        pnl = wx.Panel(self)

        # list of choices
        lblList = ['Radio One', 'Radio Two']

        # create radio box containing above list
        self.rbox = wx.RadioBox(pnl, label ='RadioBox', pos =(80, 10), choices = lblList,
                                         majorDimension = 1, style = wx.RA_SPECIFY_ROWS)

        # print True if item is not hidden
        print (self.rbox.IsItemShown(1))

        # set frame in centre
        self.Centre()
        # set size of frame
        self.SetSize((400, 250))
        # show output frame
        self.Show(True)

# wx App instance
ex = wx.App()
# Example instance
FrameUI(None, 'RadioButton and RadioBox')
ex.MainLoop()
```

**控制台输出:**

```
True
```

**输出窗口:**
![](img/244dc2ee63e75cd5ef169b96a1917c6e.png)