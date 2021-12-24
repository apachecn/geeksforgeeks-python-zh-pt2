# wx xpython–wx 中的 PopStatusText()函数。状态栏

> 原文:[https://www . geesforgeks . org/wxpython-popstatustext-function-in-wx-status bar/](https://www.geeksforgeeks.org/wxpython-popstatustext-function-in-wx-statusbar/)

在本文中，我们将了解与 wx 相关联的 PopStatusText()函数。wxPython 的 StatusBar 类。PopStatusText()函数只是用来将文本恢复到上次调用 PushStatusText 之前的值。

请注意，如果同时调用了 SetStatusText，PopStatusText 将不会更改文本，也就是说，它不会覆盖对状态文本的显式更改，而只会恢复保存的文本(如果此后没有更改过的话)。

> **语法:** wx。StatusBar.PopStatusText(自身，字段=0)
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 领域 | （同 Internationalorganizations）国际组织 | 从 0 开始的字段位置。 |

**编码示例:**

```py
import wx

class Example(wx.Frame):

    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)

        self.InitUI()

    def InitUI(self):

        self.locale = wx.Locale(wx.LANGUAGE_ENGLISH)
        self.statusbar = wx.StatusBar()
        self.statusbar.Create(self, id = 1, style = wx.STB_DEFAULT_STYLE, 
                                                      name = "Status Bar")
        self.SetStatusBar(self.statusbar)
        self.SetSize((350, 250))

        self.statusbar.SetFieldsCount(2)
        self.statusbar.SetStatusWidths([150, 150])
        self.statusbar.SetStatusText("This is text after stack pop in field 1", 0)
        self.statusbar.SetStatusText("This is text after stack pop in field 2", 1)
        self.statusbar.SetStatusStyles(styles =[wx.SB_RAISED, wx.SB_SUNKEN])

        # PUSH TEXT IN STATUS TEXT STACK
        self.statusbar.PushStatusText(string ="This is pushed text for field 1", field = 0)
        self.statusbar.PushStatusText(string ="This is pushed text for field 2", field = 1)

        # POP TEXT IN STATUS TEXT STACK
        self.statusbar.PopStatusText(field = 0)

        self.statusbar.PopStatusText(field = 1)
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

**输出窗口:**
![](img/d31ff4ccb88d8b855661f8991b555593.png)