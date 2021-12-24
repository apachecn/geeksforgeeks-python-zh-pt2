# python 中的 wxPython | GetToolPacking()函数

> 原文:[https://www . geesforgeks . org/wxpython-gettoolbacking-function-in-python/](https://www.geeksforgeeks.org/wxpython-gettoolpacking-function-in-python/)

在本文中，我们将学习与 wx 相关联的 GetToolPacking()函数。wxPython 的工具栏类。GetToolPacking()函数只是返回用于打包工具的值。如果工具栏是水平的，包装用于垂直方向的间距，如果工具栏是垂直的，包装用于水平方向的间距。不需要争论。

> **语法:**
> 
> ```
> wx.ToolBar.GetToolPacking(self, packing)
> ```
> 
> **参数:**
> 
> ```
> GetToolPacking() function takes no parameters.
> ```
> 
> **返回类型:**
> 
> ```
> int
> ```

**代码示例:**

## 蟒蛇 3

```
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
        bl = self.toolbar.GetToolPacking()

        # print tools packing value
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

```
7
```

**代码示例 2:**

## 蟒蛇 3

```
import wx

class Example(wx.Frame):
    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)
        self.InitUI()

    def InitUI(self):
        self.locale = wx.Locale(wx.LANGUAGE_ENGLISH)
        pnl = wx.Panel(self)
        self.toolbar = self.CreateToolBar()
        self.toolbar.SetToolPacking(12)
        # Add Tools Using AddTool function
        rtool = self.toolbar.AddLabelTool(id = 13, label = "Tool one", bitmap = wx.Bitmap('right.png'), shortHelp ="short help 1", longHelp = "Long help associated with simple tool 1")
        stool = self.toolbar.AddLabelTool(id = 14, label = "Tool two", bitmap = wx.Bitmap('wrong.png'), shortHelp ="short help 2", longHelp = "Long help associated with simple tool 2")

        self.toolbar.Realize()
        self.SetSize((350, 250))
        self.SetTitle('Control')
        self.Centre()
        bl = self.toolbar.GetToolPacking()

        # print tools packing value
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

```
12
```