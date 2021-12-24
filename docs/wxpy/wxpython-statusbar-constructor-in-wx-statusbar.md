# wx 中的 wxPython–status bar()构造函数。状态栏

> 原文:[https://www . geesforgeks . org/wxpython-status bar-constructor-in-wx-status bar/](https://www.geeksforgeeks.org/wxpython-statusbar-constructor-in-wx-statusbar/)

**状态栏:**状态栏是一个狭窄的窗口，可以沿着框架的底部放置，以给出少量的状态信息。

在本文中，我们将了解与 wx 相关联的 StatusBar()构造函数。wxPython 的 StatusBar 类。StatusBar()构造函数将状态栏的不同属性作为其参数，如样式、名称等。

> **语法:** wx。StatusBar.StatusBar(父级，id=ID_ANY，style=STB_DEFAULT_STYLE，name=StatusBarNameStr)
> **参数:**
> 
> <figure class="table">
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 父母 | wx。基本框架 | 要附加状态栏的父框架。 |
> | 身份证明（identification） | （同 Internationalorganizations）国际组织 | 用于状态栏的标识符。 |
> | 风格 | 长的 | 状态栏的样式。 |
> | 名字 | 线 | 与 statusbar 关联的名称。 |
> 
> </figure>

**代码示例:**

## 蟒蛇 3

```py
import wx

class Example(wx.Frame):

    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)

        self.InitUI()

    def InitUI(self):

        self.locale = wx.Locale(wx.LANGUAGE_ENGLISH)

        # CREATE STATUS BAR USING STATUSBAR CONSTRUCTOR
        self.statusbar = wx.StatusBar(self, id = 1, style = wx.STB_DEFAULT_STYLE,
                                       name = "Status Bar")
        self.statusbar.SetStatusText("Hello there this is a Status Bar")
        self.SetStatusBar(self.statusbar)
        self.SetSize((350, 250))
        self.SetTitle('New Frame Title')
        self.Centre()

def main():
    app = wx.App()
    ex = Example(None)
    ex.Show()
    app.MainLoop()

if __name__ == '__main__':
    main()
```

**输出:**

![](img/3ec2cb1c33fb067ac4da6825ef6e1da8.png)