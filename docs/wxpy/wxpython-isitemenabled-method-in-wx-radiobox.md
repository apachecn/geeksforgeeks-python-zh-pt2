# wx 中的 wxPython–IsItemEnabled()方法。无线电盒

> 原文:[https://www . geeksforgeeks . org/wxpython-isitemenabled-method-in-wx-radio box/](https://www.geeksforgeeks.org/wxpython-isitemenabled-method-in-wx-radiobox/)

在本文中，我们将了解与 wx 相关联的 IsItemEnabled()方法。wxPython 的 RadioBox 类。IsItemEnabled()方法仅用于在启用项目时返回 True，或者在使用 Enable 禁用项目时返回 False。

注意，这个函数目前只在 wxMSW、wxGTK、QT 和 wxUniversal 中实现，在其他端口总是返回 True。

> **语法:** wx。RadioBox.IsItemEnabled(self，n)
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

        # create radio boc containing above list
        self.rbox = wx.RadioBox(pnl, label ='RadioBox', pos =(80, 10), choices = lblList,
                                         majorDimension = 1, style = wx.RA_SPECIFY_ROWS)

        # print True if item at index 0 is enabled
        print (self.rbox.IsItemEnabled(0))

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
![](img/f32eda796063b23b1250852322db8835.png)