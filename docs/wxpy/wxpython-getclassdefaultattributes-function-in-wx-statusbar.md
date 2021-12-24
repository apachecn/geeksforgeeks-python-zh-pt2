# wx Tyson–wx 中的 GetClassDefaultAttributes()函数。状态栏

> 原文:[https://www . geesforgeks . org/wxpython-getclassdefaultattributes-function-in-wx-status bar/](https://www.geeksforgeeks.org/wxpython-getclassdefaultattributes-function-in-wx-statusbar/)

在本文中，我们将了解与类 wx 相关联的 GetClassDefaultAttributes()。wxPython 的 StatusBar。GetClassDefaultAttributes()用于返回 statusbar 的视觉属性，如背景色、前景色、用于控制标签/文本的字体。

> **语法:**
> 
> ```py
> wx.ToolBar.GetClassDefaultAttributes(variant=WINDOW_VARIANT_NORMAL)
> 
> ```
> 
> **返回类型:** wx。可视化属性
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 不同的 | windowVarian | 窗口的不同样式 |

**代码示例:**

```py
import wx

class Example(wx.Frame):

    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)

        self.InitUI()

    def InitUI(self):

        self.locale = wx.Locale(wx.LANGUAGE_ENGLISH)
        self.statusbar = wx.StatusBar()
        self.statusbar.Create(self, id = 1, 
                              style = wx.STB_DEFAULT_STYLE,
                              name = "Status Bar")
        self.SetStatusBar(self.statusbar)
        self.SetSize((350, 250))

        # Get wx.VisualAttributes object
        va = self.statusbar.GetClassDefaultAttributes(variant = wx.WINDOW_VARIANT_NORMAL)

        # Print Background Colour
        print(va.colBg)
        # Print Fore Ground Colour
        print(va.colFg)
        # Print Identifier for font family
        print(va.font.Family)
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

```py
(240, 240, 240, 255)
(0, 0, 0, 255)
70

```

**输出窗口:**
![](img/3ec2cb1c33fb067ac4da6825ef6e1da8.png)