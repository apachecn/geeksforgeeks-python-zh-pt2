# wx python–wx 中的 GetItemLabel()函数。收音机盒〔t1〕

> 原文:[https://www . geeksforgeeks . org/wxpython-getitem label-function-in-wx-radio box/](https://www.geeksforgeeks.org/wxpython-getitemlabel-function-in-wx-radiobox/)

在本文中，我们将了解与 wx 相关联的 GetItemLabel()函数。wxPython 的 RadioBox 类。GetItemLabel()函数只是用来返回单选框中第 n 项的文本。
以项目索引为参数。

> **语法:** wx。RadioBox.GetItemLabel(自我，n)
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | n | （同 Internationalorganizations）国际组织 | 从零开始的项索引。 |
> 
> **返回类型:**字符串

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

        # print label of item at index 1
        print (self.rbox.GetItemLabel(1))

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

```py
Radio Two

```

**输出窗口:**
![](img/f32eda796063b23b1250852322db8835.png)