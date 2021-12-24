# wxPython 中的 wxPython | GetToolSeparation()函数

> 原文:[https://www . geeksforgeeks . org/wxpython-gettool separation-function-in-wxpython/](https://www.geeksforgeeks.org/wxpython-gettoolseparation-function-in-wxpython/)

在本文中，我们将了解与 wx 相关联的 GetToolSeparation()函数。wxPython 的工具栏类。函数的作用是:返回默认的分隔符大小。GetToolSeparation()函数不接受参数。

> **语法:**
> 
> ```py
> wx.ToolBar.GetToolSeparation(self)
> 
> ```
> 
> **参数:**
> 
> ```py
> GetToolSeparation() function takes no arguments.
> 
> ```
> 
> **返回:**
> 
> ```py
> Returns the default separator size.
> 
> ```
> 
> **返回类型:**
> 
> ```py
> int
> 
> ```

**示例#1:**

```py
import wx

class Example(wx.Frame):
    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)
        self.InitUI()

    def InitUI(self):
        self.locale = wx.Locale(wx.LANGUAGE_ENGLISH)
        pnl = wx.Panel(self)
        self.toolbar = self.CreateToolBar()

        # Add Tools Using AddTool function
        rtool = self.toolbar.AddLabelTool(id = 13, label = "Tool one", bitmap = wx.Bitmap('right.png'), shortHelp ="short help 1", longHelp = "Long help associated with simple tool 1")
        stool = self.toolbar.AddLabelTool(id = 14, label = "Tool two", bitmap = wx.Bitmap('wrong.png'), shortHelp ="short help 2", longHelp = "Long help associated with simple tool 2")

        self.toolbar.Realize()
        self.SetSize((350, 250))
        self.SetTitle('Control')
        self.Centre()

        # print tool separation value
        print(self.toolbar.GetToolSeparation())

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
0

```

**例 2:**

```py
import wx

class Example(wx.Frame):
    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)
        self.InitUI()

    def InitUI(self):
        self.locale = wx.Locale(wx.LANGUAGE_ENGLISH)
        pnl = wx.Panel(self)
        self.toolbar = self.CreateToolBar()
        self.toolbar.SetToolSeparation(12)
        # Add Tools Using AddTool function
        rtool = self.toolbar.AddLabelTool(id = 13, label = "Tool one", bitmap = wx.Bitmap('right.png'), shortHelp ="short help 1", longHelp = "Long help associated with simple tool 1")
        stool = self.toolbar.AddLabelTool(id = 14, label = "Tool two", bitmap = wx.Bitmap('wrong.png'), shortHelp ="short help 2", longHelp = "Long help associated with simple tool 2")

        self.toolbar.Realize()
        self.SetSize((350, 250))
        self.SetTitle('Control')
        self.Centre()

        # print tool separation value
        print(self.toolbar.GetToolSeparation())

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
12

```