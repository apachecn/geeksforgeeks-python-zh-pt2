# wx 中的 wxPython | GetToolShortHelp()函数。工具栏

> 原文:[https://www . geesforgeks . org/wxpython-gettoolshothelp-function-in-wx-toolbar/](https://www.geeksforgeeks.org/wxpython-gettoolshorthelp-function-in-wx-toolbar/)

在本文中，我们将了解与 wx 相关联的 GetToolShortHelp()函数。wxPython 的工具栏类。函数的作用是:返回与特定工具相关的简短帮助字符串。我只接受 toolId 作为参数。

> **语法**
> 
> ```py
> wx.ToolBar.GetToolShortHelp(self, toolId)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 椅子 | （同 Internationalorganizations）国际组织 | 工具栏中工具的标识符。 |
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
        # Add Tools Using AddTool function
        rtool = self.toolbar.AddLabelTool(13, 'oneTool', wx.Bitmap('wrong.png'), shortHelp ="short help string one")
        stool = self.toolbar.AddLabelTool(14, 'twoTool', wx.Bitmap('user.png'), shortHelp ="short help string two")

        self.toolbar.Realize()
        self.SetSize((350, 250))
        self.SetTitle('Control')
        self.Centre()

        str = self.toolbar.GetToolShortHelp(13)

        # print wx.ToolBarToolBase object o tool
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
short help string one

```

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

        str = self.toolbar.GetToolShortHelp(13)+" "+self.toolbar.GetToolShortHelp(14)

        # print short help string
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
short help string one short help string two

```