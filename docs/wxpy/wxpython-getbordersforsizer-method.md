# wxPython–getborderforsizer()方法

> 原文:[https://www . geesforgeks . org/wxpython-getborderforsizer-method/](https://www.geeksforgeeks.org/wxpython-getbordersforsizer-method/)

在本文中，我们将了解与 wx 相关联的 GetBordersForSizer()方法。wxPython 的 StaticBox 类。GetBordersForSizer()是一个简单的函数，用于返回 StaticBox 中边框可能需要的额外空间。

> **语法:** wx。getborderforsizer(自身)
> **参数**在 getborderforsizer()中不需要参数。

**返回类型:**元组
T3】返回: ( borderTop，borderrother)
**代码示例:**

## 蟒蛇 3

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

        # create static box
        self.sb = wx.StaticBox(pnl, 2, label ="Static Box",
                               pos =(20, 20), size =(100, 100))

        # extra space for border
        print(self.sb.GetBorderdForSize())

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
(0, 0)
```

**输出窗口:**

![](img/a3fa988c452c4c94dbcfbfaa6b47c076.png)