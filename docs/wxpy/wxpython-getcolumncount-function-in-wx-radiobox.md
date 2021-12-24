# wx 中的 wxPython–GetColumnCount()函数。无线电盒

> 原文:[https://www . geesforgeks . org/wxpython-getcolumncount-function-in-wx-radio box/](https://www.geeksforgeeks.org/wxpython-getcolumncount-function-in-wx-radiobox/)

在本文中，我们将了解与 wx 相关联的 GetColumnCount()函数。wxPython 的 RadioBox 类。函数的作用是:简单地返回 radiobox 中的列数。
GetColumnCount()函数不需要参数。

> **语法:** wx。RadioBox.GetColumnCount(自我)
> 
> **参数:**GetColumnCount()函数不需要参数。
> 
> **返回类型:**
> int

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

        # print total columns in radio box
        print (self.rbox.GetColumnCount())

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
1

```

**输出窗口:**
![](img/f32eda796063b23b1250852322db8835.png)