# wx xpython–wx 中的 SetToolShortHelp()函数。工具栏

> 原文:[https://www . geesforgeks . org/wxpython-settooshorthelp-function-in-wx-toolbar/](https://www.geeksforgeeks.org/wxpython-settoolshorthelp-function-in-wx-toolbar/)

在本文中，我们将学习与 wx 相关联的 SetToolShortHelp()函数。wxPython 的工具栏类。SetToolShortHelp()只是为给定的工具设置简短的帮助。
它需要两个参数，即 toolId 和 helpString(新的短帮助字符串)。

> **语法:**
> 
> ```py
> wx.ToolBar.SetToolShortHelp(self, toolId, helpString)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 椅子 | （同 Internationalorganizations）国际组织 | 传递给添加工具的有问题工具的标识。 |
> | 帮助字符串 | 线 | 简短帮助的字符串。 |

**代码示例 1:**

```py
import wx

class Example(wx.Frame):

    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)
        self.InitUI()

    def InitUI(self):
        self.locale = wx.Locale(wx.LANGUAGE_ENGLISH)
        self.toolbar = self.CreateToolBar()

        td = self.toolbar.AddTool(1, 'right', wx.Bitmap('right.png'))
        te = self.toolbar.AddTool(2, 'wrong', wx.Bitmap('wrong.png'))

        # set separation of toolbar to 20
        self.toolbar.SetToolShortHelp(toolId = 1, helpString ="new short help")

        self.toolbar.Realize()
        self.Bind(wx.EVT_TOOL, self.OnOne, td)

        self.SetSize((350, 250))
        self.SetTitle('Undo redo')
        self.Centre()

    def OnOne(self, e):
        print(self.toolbar.GetToolSeparation())
        # Realize() called to finalize new added tools
        self.toolbar.Realize()

    def OnQuit(self, e):
        self.Close()

def main():

    app = wx.App()
    ex = Example(None)
    ex.Show()
    app.MainLoop()

if __name__ == '__main__':
    main()
```

**输出:**
![](img/6ec48e7a70d02563d1d96c80b4b9ac4a.png)