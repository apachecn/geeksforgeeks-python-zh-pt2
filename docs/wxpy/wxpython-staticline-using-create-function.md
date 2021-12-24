# wxPython–使用 Create()功能的静态线

> 原文:[https://www . geesforgeks . org/wxpython-static line-using-create-function/](https://www.geeksforgeeks.org/wxpython-staticline-using-create-function/)

在本文中，我们将学习与 wx 相关联的 Create()方法。wxPython 的 StaticLine 类。静态行只是可以在对话框中用来分隔控件组的行。Create()函数使用两步创建来创建 Staticline。

这条线可以是垂直的，也可以是水平的。此外，并不是所有的端口(尤其不是 wxGTK)都支持指定线的横向方向(例如水平线的高度)，因此为了最大程度的可移植性，您应该将其指定为 DefaultCoord。

> **语法:** wx。StaticLine.Create(父，id=ID_ANY，pos=DefaultPosition，size=DefaultSize，style=LI_HORIZONTAL，name=StaticLineNameStr)
> 
> **参数**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 父母 | wx。窗户 | 父窗口。不得为无。 |
> | 身份证明（identification） | wx.窗口标识 | 窗口标识符。值 wx。标识 _ 任意表示默认值。 |
> | 刷卡机 | wx。要点 | 窗口位置。如果 wx。如果指定了默认位置，则选择默认位置。 |
> | 大小 | wx。大小 | 尺寸。请注意，高度或宽度(取决于线条是水平还是垂直)将被忽略。 |
> | 风格 | 长的 | 窗口样式(wx。LI _ 水平或 wx。LI _ 垂直)。 |
> | 名字 | 线 | 窗口名称 |

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
        hlist = ['Item One', 'Item Two']
        vlist =['Item One', 'Item Two']

        # initialize a static line
        self.sl = wx.StaticLine()

        # add attributes using Create()  function
        self.sl.Create(pnl, 2,  pos =(50, 0), size = (1, 250),
                                     style = wx.LI_VERTICAL)

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

![](img/b9eed1781e23f64a0a0e05e6c121220e.png)