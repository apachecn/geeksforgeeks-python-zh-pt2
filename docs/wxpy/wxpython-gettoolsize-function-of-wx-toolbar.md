# wx 的 wxPython | GetToolSize()函数。工具栏

> 原文:[https://www . geesforgeks . org/wxpython-gettoolsize-function-of-wx-toolbar/](https://www.geeksforgeeks.org/wxpython-gettoolsize-function-of-wx-toolbar/)

在本文中，我们将了解与 wx 相关联的 GetToolSize()函数。wxPython 的工具栏类。GetToolSize()函数返回整个按钮的大小，由于增加了 3D 效果，通常比工具位图大。不需要争论。

> **语法:**
> 
> ```py
> wx.ToolBar.GetToolSize(self)
> 
> ```
> 
> **参数:**
> 
> ```py
> GetToolSize() function takes no parameters.
> 
> ```
> 
> **返回类型:**
> 
> ```py
> wx.Size
> 
> ```

**代码示例 1:**

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
        rtool = self.toolbar.AddLabelTool(13, 'oneTool', wx.Bitmap('wrong.png'), shortHelp ="short help string one")
        stool = self.toolbar.AddLabelTool(14, 'twoTool', wx.Bitmap('user.png'), shortHelp ="short help string two")

        self.toolbar.Realize()
        self.SetSize((350, 250))
        self.SetTitle('Control')
        self.Centre()

        str = self.toolbar.GetToolSize()

        # print size
        print(str)

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
(39, 38)

```

**代码示例 2:**

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
        rtool = self.toolbar.AddLabelTool(13, 'oneTool', wx.Bitmap('user.png'), shortHelp ="short help string one")
        self.toolbar.Realize()
        self.SetSize((350, 250))
        self.SetTitle('Control')
        self.Centre()

        str = self.toolbar.GetToolSize()

        # print size
        print(str)

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
(31, 30)

```