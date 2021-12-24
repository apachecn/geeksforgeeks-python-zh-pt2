# wx Tyson–wx 中的 SetToolSeparation()函数。工具栏

> 原文:[https://www . geesforgeks . org/wxpython-settool separation-function-in-wx-toolbar/](https://www.geeksforgeeks.org/wxpython-settoolseparation-function-in-wx-toolbar/)

在本文中，我们将学习与 wx 相关联的 SetToolSeparation()函数。wxPython 的工具栏类。SetToolSeparation()设置默认的分隔符大小。默认值为 5。SetToolSeparation()函数只将 Separation()作为参数。

> **语法:**
> 
> ```py
> wx.ToolBar.SetToolSeparation(self, separation)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 分离 | （同 Internationalorganizations）国际组织 | 分隔符大小。 |

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
        te = self.toolbar.AddTool(2, 'wrong', wx.Bitmap('wrong.png'))

        # set separation of toolbar to 20
        self.toolbar.SetToolSeparation(separation = 20)

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

```py
20

```