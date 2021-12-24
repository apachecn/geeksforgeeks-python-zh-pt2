# wx xpython–wx 中的 EnableItem()函数。无线电盒

> 原文:[https://www . geesforgeks . org/wxpython-enable item-function-in-wx-radio box/](https://www.geeksforgeeks.org/wxpython-enableitem-function-in-wx-radiobox/)

在本文中，我们将了解与 wx 相关联的 EnableItem()函数。wxPython 的 RadioBox 类。EnableItem()函数只是用来启用或禁用单选按钮框中的单个按钮。
取按钮位置禁用或启用，布尔‘启用’为真启用，假禁用。

> **语法:** wx。启用项目(自身，n，启用=真)
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | n | （同 Internationalorganizations）国际组织 | 要启用或禁用的从零开始的按钮。 |
> | 使能够 | 弯曲件 | 如果为真，则启用；如果为假，则禁用。 |
> 
> **返回类型:** bool

**代码示例:**

```py
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
                                majorDimension = 1, style = wx.RA_SPECIFY_COLS)

        # disable the second button in radio box
        self.rbox.EnableItem(1, False)

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

**代码输出:**
![](img/f32eda796063b23b1250852322db8835.png)