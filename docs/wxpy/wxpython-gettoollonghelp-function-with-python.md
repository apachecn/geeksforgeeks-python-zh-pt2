# wxPython | gettoolonghelp()函数配合 python

> 原文:[https://www . geesforgeks . org/wxpython-gettoolonghelp-function-with-python/](https://www.geeksforgeeks.org/wxpython-gettoollonghelp-function-with-python/)

在本文中，我们将学习 wx 中的 GetToolLongHelp()函数。wxPython 的工具栏类。GetToolLongHelp()函数返回给定工具的长帮助。它只接受一个参数，即 toolid(所讨论的工具的 id，传递给 AddTool)。

> **语法:**
> 
> ```py
> wx.GetToolLongHelp(self, toolid)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 椅子 | （同 Internationalorganizations）国际组织 | 一个整数，通过它可以在后续操作中识别工具。 |
> 
> **返回类型:**
> 
> ```py
> string
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
        self.toolbar.SetMargins(10, 10)
        # Add Tools Using AddTool function
        rtool = self.toolbar.AddLabelTool(id = 13, label = "Tool one", bitmap = wx.Bitmap('wrong.png'), shortHelp ="short help 1", longHelp = "Long help associated with simple tool 1")
        stool = self.toolbar.AddLabelTool(id = 14, label = "Tool two", bitmap = wx.Bitmap('wrong.png'), shortHelp ="short help 2", longHelp = "Long help associated with simple tool 2")

        self.toolbar.Realize()
        self.SetSize((350, 250))
        self.SetTitle('Control')
        self.Centre()

        bl = self.toolbar.GetToolLongHelp(13)

        # print tool longHelp string
        print(bl)

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
Long help associated with simple tool 1

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
        self.toolbar.SetMargins(10, 10)
        # Add Tools Using AddTool function
        rtool = self.toolbar.AddLabelTool(id = 13, label = "Tool one", bitmap = wx.Bitmap('wrong.png'), shortHelp ="short help 1", longHelp = "Long help associated with simple tool 1")
        stool = self.toolbar.AddLabelTool(id = 14, label = "Tool two", bitmap = wx.Bitmap('wrong.png'), shortHelp ="short help 2", longHelp = "Long help associated with simple tool 2")

        self.toolbar.Realize()
        self.SetSize((350, 250))
        self.SetTitle('Control')
        self.Centre()

        bl = self.toolbar.GetToolLongHelp(14)

        # print tool longHelp string
        print(bl)

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
Long help associated with simple tool 2

```