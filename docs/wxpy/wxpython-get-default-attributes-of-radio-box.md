# wxPython |获取收音盒默认属性

> 原文:[https://www . geesforgeks . org/wxpython-get-default-attributes-of-radio-box/](https://www.geeksforgeeks.org/wxpython-get-default-attributes-of-radio-box/)

在本文中，我们将了解与 wx 相关联的 GetClassDefaultAttributes()函数。wxPython 的 RadioBox 类。GetClassDefaultAttributes()函数用于返回 wx。VisualAttributes 对象，用于与单选框关联的属性，如背景色、前景色和字体。
它以变式作为论证论据。

> **语法:** wx。
> 参数:
> 
> <figure class="table">
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 不同的 | WindowVariant | 无线电盒的变体。 |
> 
> </figure>
> 
> **返回类型:** wx。视觉属性

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

        # list of choices
        lblList = ['Radio One', 'Radio Two']

        # create radio boc containing above list
        self.rbox = wx.RadioBox(pnl, label ='RadioBox', pos =(80, 10), choices = lblList,
                                majorDimension = 1, style = wx.RA_SPECIFY_COLS)

        # create wx.VisualAttributes object
        vb = self.rbox.GetClassDefaultAttributes()

        # print Background Colour
        print (vb.colBg)

        # print Foreground Colour
        print (vb.colFg)

        # print Background Colour
        print (vb.font)

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
(247, 247, 247, 255)
(61, 61, 61, 255)
<wx._gdi.Font; proxy of  >
```

**输出窗口:**

![](img/f32eda796063b23b1250852322db8835.png)