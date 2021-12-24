# wx 中的 wxPython–GetString()方法。无线电盒

> 原文:[https://www . geesforgeks . org/wxpython-getstring-method-in-wx-radio box/](https://www.geeksforgeeks.org/wxpython-getstring-method-in-wx-radiobox/)

在本文中，我们将学习与 wx 相关联的 GetString()方法。wxPython 的 RadioBox 类。GetString()方法只是用来返回具有给定索引的项的标签。

它以对应项的索引为参数。

> **语法:** wx。RadioBOx.GetString(自我，n)
> 
> **参数**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | n | （同 Internationalorganizations）国际组织 | 从零开始的索引。 |
> 
> **返回:**项目的标签，如果位置无效，则返回空字符串。
> 
> **返回类型:**字符串

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

        # set tooltip for first tool
        self.rbox.SetItemToolTip(0, "Item One")

        # print the label string of item at index 0
        print (self.rbox.GetString(0))

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
Radio One

```

**输出窗口:**
![](img/cc8bfdda21317a190ad16d2a2f994a74.png)