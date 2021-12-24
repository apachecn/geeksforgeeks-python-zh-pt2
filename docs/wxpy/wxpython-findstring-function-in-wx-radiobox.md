# wx 中的 wxPython–find string()函数。无线电盒

> 原文:[https://www . geesforgeks . org/wxpython-find string-function-in-wx-radio box/](https://www.geeksforgeeks.org/wxpython-findstring-function-in-wx-radiobox/)

在本文中，我们将了解与 wx 相关联的 FindString()函数。wxPython 的 RadioBox 类。FindString()函数只是用来查找与给定字符串匹配的按钮，如果找到就返回位置，如果没有找到就返回 NOT_FOUND。

它需要一个字符串参数来匹配字符串和布尔值。如果区分大小写，则为真；否则为假。

> **语法:** wx。查找字符串(自身，字符串，bCase =假)
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 线 | 线 | 要查找的字符串。 |
> | bCase | 弯曲件 | 搜索应该区分大小写吗？ |
> 
> **返回:**从零开始返回匹配按钮的索引。
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
        lblList = ['Radio One', 'Radio Two']

        # create radio boc containing above list
        self.rbox = wx.RadioBox(pnl, label ='RadioBox', pos =(80, 10), choices = lblList,
                                 majorDimension = 1, style = wx.RA_SPECIFY_COLS)

        # print the position of matching string button
        print (self.rbox.FindString('radio two'))

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
1

```

**输出窗口:**
![](img/f32eda796063b23b1250852322db8835.png)