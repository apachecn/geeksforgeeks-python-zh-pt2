# wx xpython–wx 中的 SetMargins()函数。工具栏

> 原文:[https://www . geesforgeks . org/wxpython-setmargins-function-in-wx-toolbar/](https://www.geeksforgeeks.org/wxpython-setmargins-function-in-wx-toolbar/)

在本文中，我们将学习与 wx 相关的 SetMargins()函数。wxPython 的工具栏类。函数的作用是:设置用作工具栏边距的值。它采用两个整数 x 和 y 作为左右边距的参数。

> **语法:**
> 
> ```
> wx.ToolBar.SetMargins(self, x, y)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | x | （同 Internationalorganizations）国际组织 | 左边距、右边距和工具间间隔值。 |
> | y | （同 Internationalorganizations）国际组织 | 上边距、下边距和工具间间隔值。 |
> 
> **返回类型:**
> 
> ```
> wx.ToolBarToolBase
> 
> ```

**代码示例 1:**

```
import wx

class Example(wx.Frame):

    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)
        self.InitUI()

    def InitUI(self):
        self.locale = wx.Locale(wx.LANGUAGE_ENGLISH)
        self.toolbar = self.CreateToolBar()
        self.toolbar.SetMargins(20, 10)
        td = self.toolbar.AddTool(1, 'right', wx.Bitmap('right.png'))
        self.toolbar.Realize()
        print(self.toolbar.GetMargins())
        self.SetSize((350, 250))
        self.SetTitle('Undo redo')
        self.Centre()

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

```
(20, 10)

```