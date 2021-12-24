# wx xpython–wx 中的 SetSelection()方法。无线电盒

> 原文:[https://www . geesforgeks . org/wxpython-set selection-method-in-wx-radio box/](https://www.geeksforgeeks.org/wxpython-setselection-method-in-wx-radiobox/)

在本文中，我们将学习与 wx 相关的 SetSelection()方法。wxPython 的 RadioBox 类。SetSelection()设置单选按钮组中指定项目的工具提示文本。

该功能目前仅在 wxMSW 和 wxGTK2 中实现，在其他端口中不执行任何操作。

> **语法:** wx。单选框。设置选择(自身，项目)
> 
> **参数**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | n | （同 Internationalorganizations）国际组织 | 从零开始的项索引。 |

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

        # create radio box containing above list
        self.rbox = wx.RadioBox(pnl, label ='RadioBox', pos =(80, 10), choices = lblList,
                                         majorDimension = 1, style = wx.RA_SPECIFY_ROWS)

        # set item at index 1 be selected
        self.rbox.SetSelection(1)

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

**输出窗口:**
![](img/98ffd945f257f8a1a7a26319cc51b453.png)