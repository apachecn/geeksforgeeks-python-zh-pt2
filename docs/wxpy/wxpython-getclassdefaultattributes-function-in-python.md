# python 中的 wxPython | GetClassDefaultAttributes()函数

> 原文:[https://www . geesforgeks . org/wxpython-getclassdefaultattributes-python 中的函数/](https://www.geeksforgeeks.org/wxpython-getclassdefaultattributes-function-in-python/)

在本文中，我们将学习 wx 类的 GetClassDefaultAttributes()。wxPython 的工具栏。GetClassDefaultAttributes()用于返回工具栏的视觉属性，如背景色、前景色、用于控制标签/文本的字体。

**参数:**

| 参数 | 输入类型 | 描述 |
| --- | --- | --- |
| 不同的 | windowVarian | 窗口的不同样式 |

**语法:**

```py
wx.ToolBar.GetClassDefaultAttributes(variant=WINDOW_VARIANT_NORMAL)

```

**返回类型:**

```py
wx.VisualAttributes

```

**代码示例:**

```py
import wx

class Example(wx.Frame):
    global count
    count = 0;

    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)

        self.InitUI()

    def InitUI(self):
        self.locale = wx.Locale(wx.LANGUAGE_ENGLISH)
        pnl = wx.Panel(self)
        self.toolbar = self.CreateToolBar()
        # Add Tools Using AddTool function
        rtool = self.toolbar.AddTool(13, 'twoTool', wx.Bitmap('wrong.png'), shortHelp ="Simple Tool2")

        self.toolbar.Realize()
        self.SetSize((350, 250))
        self.SetTitle('Control')
        self.Centre()

        # get Visual attribute object
        t = self.toolbar.GetClassDefaultAttributes(variant = wx.WINDOW_VARIANT_NORMAL)
        # print background color ratio
        print(t.colBg)
        # print foreground color ratio
        print(t.colFg)
        # print wx.Font object
        print(t.font)

def main():
    app = wx.App()
    ex = Example(None)
    ex.Show()
    app.MainLoop()

if __name__ == '__main__':
    main()
```

**输出:**

```py
(240, 240, 240, 255)
(0, 0, 0, 255)
<wx._core.Font object at 0x00000080FC7B5280>

```