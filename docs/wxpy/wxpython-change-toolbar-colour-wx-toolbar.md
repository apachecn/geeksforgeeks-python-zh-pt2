# wxPython–更改工具栏颜色 wx。工具栏

> 原文:[https://www . geesforgeks . org/wxpython-change-toolbar-color-wx-toolbar/](https://www.geeksforgeeks.org/wxpython-change-toolbar-colour-wx-toolbar/)

在这篇文章中，我们将学习改变工具栏的颜色。为了做到这一点，我们将简单地使用 SetBackgroundColour()函数。SetBackgroundColour() dimply 设置窗口的背景颜色。它有一个 wx。颜色参数，即用作背景颜色的颜色。

> **语法:** wx。工具栏。设置背景颜色(自身，颜色)
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 颜色 | wx。颜色 | 用作背景色的颜色 |
> 
> **返回类型:** bool
> 
> **返回:**如果颜色真的改变了，则为真；如果颜色已经设置为这种颜色，但没有进行任何操作，则为假。

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

        # Add tools to toolbar
        ptool = self.toolbar.AddTool(12, 'oneTool',
                                     wx.Bitmap('right.png'),
                                     wx.Bitmap('wrong.png'), shortHelp ="Simple Tool")

        qtool = self.toolbar.AddTool(12, 'oneTool', wx.Bitmap('wrong.png'),
                                     wx.Bitmap('wrong.png'), shortHelp ="Simple Tool")

        # change background colour of toolbar
        self.toolbar.SetBackgroundColour((255, 200, 50, 255))

        self.toolbar.Realize()
        self.SetSize((350, 250))
        self.SetTitle('Control')
        self.Centre()

def main():
    app = wx.App()
    ex = Example(None)
    ex.Show()
    app.MainLoop()

if __name__ == '__main__':
    main()
```

**输出窗口:**
![](img/81cc756735dece8346bcf52189fae05b.png)