# python 中的 wxPython | GetToolByPos()函数

> 原文:[https://www . geeksforgeeks . org/wxpython-gettoolby pos-python 中的函数/](https://www.geeksforgeeks.org/wxpython-gettoolbypos-function-in-python/)

在本文中，我们将学习 wx 中的 GetToolByPos()函数。wxPython 的工具栏类。GetToolByPos()函数用于简单地返回一个指向工具特定位置的指针。
GetToolByPos()函数接受一个参数，即 Pos(刀具位置)。

> **语法:**
> 
> ```
> wx.ToolBar.GetToolByPos(self, pos)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 刷卡机 | （同 Internationalorganizations）国际组织 | 工具的位置从 0 开始。 |
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
        self.toolbar.SetMargins(10, 10)
        # Add Tools Using AddTool function
        rtool = self.toolbar.AddTool(13, 'Toolone', wx.Bitmap('wrong.png'), shortHelp ="Simple Tool2")
        stool = self.toolbar.AddTool(14, 'Tooltwo', wx.Bitmap('wrong.png'), shortHelp ="Simple Tool")

        self.toolbar.Realize()
        self.SetSize((350, 250))
        self.SetTitle('Control')
        self.Centre()

        obj = self.toolbar.GetToolByPos(1)

        # print tool label
        print(obj.GetLabel())

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
Tooltwo

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
        self.toolbar.SetMargins(10, 10)
        # Add Tools Using AddTool function
        rtool = self.toolbar.AddTool(13, 'Toolone', wx.Bitmap('wrong.png'), shortHelp ="Simple Tool2")
        stool = self.toolbar.AddTool(14, 'Tooltwo', wx.Bitmap('wrong.png'), shortHelp ="Simple Tool")

        self.toolbar.Realize()
        self.SetSize((350, 250))
        self.SetTitle('Control')
        self.Centre()

        obj = self.toolbar.GetToolByPos(0)

        # print tool label
        print(obj.GetLabel())

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
Toolone

```