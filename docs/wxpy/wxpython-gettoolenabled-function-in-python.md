# python 中的 wxPython | GetToolEnabled()函数

> 原文:[https://www . geeksforgeeks . org/wxpython-gettool enabled-python 中的函数/](https://www.geeksforgeeks.org/wxpython-gettoolenabled-function-in-python/)

在本文中，我们将学习 wx 类中的 GetToolEnabled()函数。wxPython 的工具栏。GetToolEnabled()函数只是在特定位置返回一个指向工具的指针。它只接受一个 pos 参数(工具的位置从 0 开始)。

> **语法:**
> 
> ```py
> wx.ToolBar.GetToolEnabled(self, toolid)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 椅子 | （同 Internationalorganizations）国际组织 | 传递给添加工具的有问题工具的标识。 |
> 
> **返回类型:**
> 
> ```py
> True if the tool is enabled, False otherwise.
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
        self.toolbar.SetMargins(10, 10)
        # Add Tools Using AddTool function
        rtool = self.toolbar.AddTool(13, 'Toolone', wx.Bitmap('wrong.png'), shortHelp ="Simple Tool2")
        stool = self.toolbar.AddTool(14, 'Tooltwo', wx.Bitmap('wrong.png'), shortHelp ="Simple Tool")

        self.toolbar.Realize()
        self.SetSize((350, 250))
        self.SetTitle('Control')
        self.Centre()

        bl = self.toolbar.GetToolEnabled(13)

        # print True of enabled
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
True

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
        rtool = self.toolbar.AddTool(13, 'Toolone', wx.Bitmap('wrong.png'), shortHelp ="Simple Tool2")
        stool = self.toolbar.AddTool(14, 'Tooltwo', wx.Bitmap('wrong.png'), shortHelp ="Simple Tool")
        self.toolbar.Realize()
        self.toolbar.EnableTool(14, False)
        self.SetSize((350, 250))
        self.SetTitle('Control')
        self.Centre()

        bl = self.toolbar.GetToolEnabled(14)

        # print True of enabled
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
False

```