# wx 中的 wxPython–static text()构造函数。StaticText

> 原文:[https://www . geesforgeks . org/wxpython-static text-constructor-in-wx-static text/](https://www.geeksforgeeks.org/wxpython-statictext-constructor-in-wx-statictext/)

在本文中，我们将了解与 wx 相关联的 StaticText()。wxPython 的 StaticText 类。静态文本控件显示一行或多行只读文本。

wx。StaticText 支持三种经典的文本对齐方式:标签省略，即如果标签不适合所提供的空间，则用省略号(“…”)替换部分文本，以及用 wx 格式化标记。控件。设置标签标记。

> **语法:** wx。StaticText.StaticText(parent，id=ID_ANY，label= " "，pos=DefaultPosition，size=DefaultSize，style=0，name=StaticTextNameStr)
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 父母 | wx。窗户 | 父窗口。不应该是无。 |
> | 身份证明（identification） | wx。窗户 | 父窗口。不应该是无。 |
> | 父母 | wx.窗口标识 | 控件标识符。值-1 表示默认值。 |
> | 标签 | 线 | 标示文字。 |
> | 刷卡机 | wx。要点 | 窗口位置。 |
> | 大小 | wx。大小 | 窗口大小。 |
> | 风格 | 长的 | 窗口样式。 |
> | 名字 | 线 | 窗口名称。 |

**代码示例:**

```
import wx

class Example(wx.Frame):

    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)
        self.InitUI()

    def InitUI(self):
        self.locale = wx.Locale(wx.LANGUAGE_ENGLISH)
        self.pnl = wx.Panel(self)
        bmp = wx.Bitmap('right.png')
        # CREATE STATICTEXT AT POINT (20, 20)
        self.st = wx.StaticText(self.pnl, id = 1, label ="This is StaticText", pos =(20, 20),
                                size = wx.DefaultSize, style = 0, name ="statictext")

        self.SetSize((350, 250))
        self.SetTitle('wx.Button')
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
![](img/c1848a18ca61eb811973e14a6083d580.png)