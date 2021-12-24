# wx 中的 wxPython–setitemholtext()方法。无线电盒

> 原文:[https://www . geeksforgeeks . org/wxpython-setitemphelptext-method-in-wx-radio box/](https://www.geeksforgeeks.org/wxpython-setitemhelptext-method-in-wx-radiobox/)

在本文中，我们将学习与 wx 相关联的 SetItemHelpText()方法。wxPython 的 RadioBox 类。方法只是用来为一个项目设置帮助文本。空字符串会删除任何现有的帮助文本。

> **语法:**wx . radio box . settemHelpText(self，item，helptext)
> 
> **参数**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 项目 | （同 Internationalorganizations）国际组织 | 从零开始的项索引。 |
> | 帮助文本 | 线 | 要为项目设置的帮助文本。 |

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

        # set help text for item at index 0
        self.rbox.SetItemHelpText(0, "First Item")

        # print helptext associated with item
        print (self.rbox.GetItemHelpText(0))

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
First Item
```

**输出窗口:**
![](img/244dc2ee63e75cd5ef169b96a1917c6e.png)