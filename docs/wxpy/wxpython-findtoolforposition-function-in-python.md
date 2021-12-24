# python 中的 wxPython | FindToolForPosition()函数

> 原文:[https://www . geeksforgeeks . org/wxpython-find toolforposition-function-in-python/](https://www.geeksforgeeks.org/wxpython-findtoolforposition-function-in-python/)

在本文中，我们将学习类 wx 的 FindToolForPosition()函数。wxPython 的工具栏。FindToolForPosition()用于为给定的鼠标位置查找工具。它获取窗口的 x 和 y 位置。

> **语法:**
> 
> ```
> wx.ToolBar.FindToolForPosition(self, x, y)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | x | （同 Internationalorganizations）国际组织 | x 位置。 |
> | y | （同 Internationalorganizations）国际组织 | y 位置。 |
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
    global count
    count = 0;

    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)

        self.InitUI()

    def InitUI(self):
        self.locale = wx.Locale(wx.LANGUAGE_ENGLISH)
        pnl = wx.Panel(self)
        self.toolbar = self.CreateToolBar()
        # Add Tools Using AddTool function
        rtool = self.toolbar.AddTool(13, 'twoTool', wx.Bitmap('wrong.png'), shortHelp ="Simple Tool2")

        self.toolbar.Realize()
        self.SetSize((350, 250))
        self.SetTitle('Control')
        self.Centre()

        # print wx.ToolBarToolBase object o tool
        print(self.toolbar.FindToolForPosition(5, 5))

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
<wx._core.ToolBarToolBase object at 0x0000009B92B041F0>

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
        self.locale = wx.Locale(wx.LANGUAGE_ENGLISH)
        pnl = wx.Panel(self)
        self.toolbar = self.CreateToolBar()
        # Add Tools Using AddTool function
        rtool = self.toolbar.AddTool(13, 'twoTool', wx.Bitmap('wrong.png'), shortHelp ="Simple Tool2")
        stool = self.toolbar.AddTool(14, 'twoTool', wx.Bitmap('user.png'), shortHelp ="Simple Tool2")
        self.toolbar.Realize()
        self.SetSize((350, 250))
        self.SetTitle('Control')
        self.Centre()

        # print wx.ToolBarToolBase object o tool
        print(self.toolbar.FindToolForPosition(40, 5).GetLabel())

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
twoTool

```