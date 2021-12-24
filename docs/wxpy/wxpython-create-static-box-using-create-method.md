# wxPython–使用 Create()方法创建静态框

> 原文:[https://www . geesforgeks . org/wxpython-create-static-box-using-create-method/](https://www.geeksforgeeks.org/wxpython-create-static-box-using-create-method/)

在本文中，我们将学习 wxPython 中的静态盒子。静态框是围绕其他窗口绘制的矩形，用于表示项目的逻辑分组。
在本文中，我们将使用两步创建来创建 Static Box，为此，我们将使用 create()方法。

> **语法:** wx。StaticBox.Create(parent，id=ID_ANY，label= "，pos=DefaultPosition，size=DefaultSize，style=0，name=StaticBoxNameStr)
> 
> **参数**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 父母 | wx。窗户 | 父窗口。不得为无。 |
> | 身份证明（identification） | wx.窗口标识 | 窗口标识符。值 wx。标识 _ 任意表示默认值。 |
> | 标签 | 线 | 要在静态框中显示的文本，空字符串表示没有标签。 |
> | 刷卡机 | wx。要点 | 窗口位置。如果 wx。如果指定了默认位置，则选择默认位置。 |
> | 大小 | wx。大小 | 复选框大小。如果 wx。如果指定了默认大小，则选择默认大小。 |
> | 风格 | 长的 | 窗口样式。没有特定于静态框的样式，但是在使用 wxGTK 时，可以在这里使用通用的 ALIGN_LEFT、ALIGN _ CENTRE _ HORIZONTAL 和 ALIGN_RIGHT 来更改静态框标签的位置 |
> | 名字 | 线 | 窗口名称 |
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

        # initialize static box
        self.sb = wx.StaticBox()

        # create static box
        self.sb.Create(pnl, 2, label ="Static Box", pos =(20, 20), size =(100, 100))

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
![](img/b0e542f2391d1e110833512be4aa17b9.png)