# wxppython–settemtooltip()方法(在 wx 中)。收音机盒〔t1〕

> 原文:[https://www . geesforgeks . org/wxpython-set item tooltip-method-in-wx-radio box/](https://www.geeksforgeeks.org/wxpython-setitemtooltip-method-in-wx-radiobox/)

在本文中，我们将学习与 wx 相关联的 SetItemToolTip()方法。wxPython 的 RadioBox 类。方法只是用来设置单选组中指定项目的工具提示文本。

该功能目前仅在 wxMSW 和 wxGTK2 中实现，在其他端口中不执行任何操作。

> **语法:** wx。RadioBox.SetItemToolTip(自我、项目、文本)
> 
> **参数**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 项目 | （同 Internationalorganizations）国际组织 | 从零开始的项索引。 |
> | 帮助文本 | 线 | 项目的工具提示文本，如果为空，工具提示将被移除。 |

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

        # set tooltip for item at index 0
        self.rbox.SetItemToolTip(0, "ToolTip item 0")

        # print tooltip for item at index 0
        print (self.rbox.GetItemToolTip(0).GetTip())
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
ToolTip item 0
```

**输出窗口:**
![](img/e24de5ff2b648ebd31118773b8ee4a3b.png)