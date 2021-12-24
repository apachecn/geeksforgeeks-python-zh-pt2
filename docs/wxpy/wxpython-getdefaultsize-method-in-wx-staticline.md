# wx 中的 wxPython–GetDefaultSize()方法。静态线

> 原文:[https://www . geesforgeks . org/wxpython-getdefaultsize-method-in-wx-static line/](https://www.geeksforgeeks.org/wxpython-getdefaultsize-method-in-wx-staticline/)

在本文中，我们将学习与 wx 相关联的方法 GetDefaultSize()。wxPython 的 StaticLine 类。GetDefaultSize()方法只是用来返回将被赋予静态行的较小维度的大小，即

水平线的高度或垂直线的宽度。

> **语法:** wx。staticline . getdefaultsize()
> 
> **参数:**GetDefaultSize()方法中不需要参数。
> 
> **返回类型:** int

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
        hlist = ['Item One', 'Item Two']
        vlist =['Item One', 'Item Two']

        # create vertical line from point (50, 0) t0 (50, 250)
        self.sl = wx.StaticLine(pnl, 2,  pos =(50, 0), size = (1, 250),  
                                              style = wx.LI_VERTICAL)

        # print size of the smaller dimension of static line
        print (self.sl.GetDefaultSize())

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
2

```

**输出窗口:**
![](img/b9eed1781e23f64a0a0e05e6c121220e.png)