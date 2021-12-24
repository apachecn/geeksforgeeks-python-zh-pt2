# Python 中的 wxPython | FindControl()函数

> 原文:[https://www . geesforgeks . org/wxpython-find control-python 中的函数/](https://www.geeksforgeeks.org/wxpython-findcontrol-function-in-python/)

在这篇特别的文章中，我们将学习 wx 的 FindControl()文章。wxPython 的工具栏类。函数的作用是:如果没有找到对应的控件，则返回一个指向 id 或 None 标识的控件的指针。它只需要一个参数“id”。

> **语法:**
> 
> ```
> wx.ToolBar.FindControl(self, id)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 身份证明（identification） | （同 Internationalorganizations）国际组织 | 控件的标识符。 |
> 
> **返回类型:**
> 
> ```
> wx.Control
> 
> ```

**代码示例 1:**

```
import wx

class Example(wx.Frame):
    global count
    count = 0;

    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)

        self.InitUI()

    def InitUI(self):
        pnl = wx.Panel(self)
        self.toolbar = self.CreateToolBar()
        ctrl = wx.Control(self.toolbar, 21, wx.DefaultPosition, wx.DefaultSize, style = 0, name ='control')
        # Add control using AddControl() method
        rtool = self.toolbar.AddControl(ctrl, 'control')
        self.toolbar.Realize()
        self.SetSize((350, 250))
        self.SetTitle('Simple toolbar')
        self.Centre()

        print(self.toolbar.FindControl(21))

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
<wx._core.Control object at 0x00000026931240D0>

```

**代码示例 2:**

```
import wx

class Example(wx.Frame):
    global count
    count = 0;

    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)

        self.InitUI()

    def InitUI(self):
        pnl = wx.Panel(self)
        self.toolbar = self.CreateToolBar()
        ctrl = wx.Control(self.toolbar, 21, wx.DefaultPosition, wx.DefaultSize, style = 0, name ='control')
        # Add control using AddControl() method
        rtool = self.toolbar.AddControl(ctrl, 'control')
        self.toolbar.Realize()
        self.SetSize((350, 250))
        self.SetTitle('Simple toolbar')
        self.Centre()

        print(self.toolbar.FindControl(21).GetName())

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
control

```