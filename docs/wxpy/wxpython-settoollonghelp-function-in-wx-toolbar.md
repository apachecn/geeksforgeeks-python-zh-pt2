# wx xpython–wx 中的 SetToolLongHelp()函数。工具栏

> 原文:[https://www . geesforgeks . org/wxpython-settoolonghelp-function-in-wx-toolbar/](https://www.geeksforgeeks.org/wxpython-settoollonghelp-function-in-wx-toolbar/)

在本文中，我们将学习与 wx 相关联的 SetToolLongHelp()函数。wxPython 的工具栏类。SetToolLongHelp()设置给定工具的长帮助。SetToolLongHelp()以 toolId 和 helpString 为参数。

> **语法:**
> 
> ```py
> wx.ToolBar.SetToolLongHelp(self, toolId, helpString)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 椅子 | （同 Internationalorganizations）国际组织 | 传递给添加工具的有问题工具的标识。 |
> | 帮助字符串 | 线 | 一根长长的救命稻草。 |

**代码示例:**

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
        # set disabled bitmap for tool wit id = 1
        self.toolbar.SetToolDisabledBitmap(id = 1, bitmap = wx.Bitmap('wrong.png'))
        self.toolbar.Realize()
        self.Bind(wx.EVT_TOOL, self.OnOne, td)

        self.SetSize((350, 250))
        self.SetTitle('Undo redo')
        self.Centre()

    def OnOne(self, e):
        # set long help string for tool
        self.toolbar.SetToolLongHelp(toolId = 1, helpString ="This is new Long Help String.")
        str = self.toolbar.GetToolLongHelp(toolId = 1)
        print(str)
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

```py
This is new Long Help String.

```