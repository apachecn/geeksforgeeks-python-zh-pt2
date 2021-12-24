# python 中的 wxPython| FindById()函数

> 原文:[https://www . geesforgeks . org/wxpython-find byid-python 中的函数/](https://www.geeksforgeeks.org/wxpython-findbyid-function-in-python/)

在本文中，我们将学习一个简单的函数，即 wx 中的 FindById()。wxPython 的工具栏类。FindById 是一个简单的函数，如果没有找到相应的工具，它会返回一个指向由 Id 或 None 标识的工具的指针。FindById()只接受一个特定工具的 Id 参数。

> **语法:**
> 
> ```py
> wx.ToolBar.FindById(self, id)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 椅子 | （同 Internationalorganizations）国际组织 | 一个整数，通过它可以在后续操作中识别工具。 |
> 
> **返回:**
> 返回指针到相应的工具。
> 
> *返回类型:*
> 
> ```py
> wx.ToolBarToolBase
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
        rtool = self.toolbar.AddTool(13, 'twoTool', wx.Bitmap('wrong.png'), shortHelp ="Simple Tool2")

        self.toolbar.Realize()
        self.SetSize((350, 250))
        self.SetTitle('Control')
        self.Centre()

        # print wx.ToolBarToolBase object o tool
        print(self.toolbar.FindById(13))

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
<wx._core.ToolBarToolBase object at 0x0000003D2DB241F0>

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
        rtool = self.toolbar.AddTool(13, 'oneTool', wx.Bitmap('wrong.png'), shortHelp ="Simple Tool1")
        stool = self.toolbar.AddTool(14, 'twoTool', wx.Bitmap('user.png'), shortHelp ="Simple Tool2")

        self.toolbar.Realize()
        self.SetSize((350, 250))
        self.SetTitle('Control')
        self.Centre()

        # print label string
        print(self.toolbar.FindById(14).GetLabel())

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
twoTool

```