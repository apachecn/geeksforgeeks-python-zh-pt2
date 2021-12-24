# python 中的 wxPython | GetMargins()函数

> 原文:[https://www . geeksforgeeks . org/wxpython-getmargins-python 中的函数/](https://www.geeksforgeeks.org/wxpython-getmargins-function-in-python/)

在本文中，我们将学习 wx 类的 GetMargins()函数。wxPython 中的工具栏。GetMargins()函数返回左/右和上/下页边距，它们也用于工具间的调整。GetMargins 不接受任何参数。

> **语法:**
> 
> ```py
> wx.ToolBar.GetMargins(self)
> 
> ```
> 
> **参数:**
> 
> ```py
> No Parameters required in GetMargins()
> 
> ```
> 
> **返回类型:**
> 
> ```py
> wx.Size
> 
> ```

**代码示例:**

```py
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
        stool = self.toolbar.AddTool(14, 'twoTool', wx.Bitmap('wrong.png'), shortHelp ="Simple Tool")

        self.toolbar.Realize()
        self.SetSize((350, 250))
        self.SetTitle('Control')
        self.Centre()

        # print x and y margin of toolbar
        print(self.toolbar.GetMargins())

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
(0, 0)

```

**代码示例:**

```py
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
        self.toolbar.SetMargins(10, 10)
        # Add Tools Using AddTool function
        rtool = self.toolbar.AddTool(13, 'twoTool', wx.Bitmap('wrong.png'), shortHelp ="Simple Tool2")
        stool = self.toolbar.AddTool(14, 'twoTool', wx.Bitmap('wrong.png'), shortHelp ="Simple Tool")

        self.toolbar.Realize()
        self.SetSize((350, 250))
        self.SetTitle('Control')
        self.Centre()

        # print x and y margin of toolbar
        print(self.toolbar.GetMargins())

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
(10, 10)

```