# python 中的 wxPython | GetToolBitmapSize()函数

> 原文:[https://www . geesforgeks . org/wxpython-gettoolbitmapsize-python 中的函数/](https://www.geeksforgeeks.org/wxpython-gettoolbitmapsize-function-in-python/)

在本文中，我们将学习 wxPython 的 GetToolBitmapSize()函数。GetToolBitmapSize()返回工具栏期望的位图大小。

默认位图大小取决于平台:例如，城市垃圾为 16×15，GTK 为 24×24。该大小不一定表示给定平台上工具栏的最佳大小，为此，您应该使用 ArtProvider::GetNativeSizeHint(wxART _ TOOLBAR)，但无论如何，由于位图大小是从与添加到工具栏的工具相关联的位图大小中自动推导出来的，因此通常没有必要显式调用 SetToolBitmapSize。

> **语法:**
> 
> ```
> wx.ToolBar.GetToolBitmapSize(self)
> ```
> 
> **参数:**
> 
> ```
> No Parameters in GetToolBitmapSize() function.
> ```
> 
> **返回类型:**
> 
> ```
> wx.Size
> ```

**代码示例:**

## 蟒蛇 3

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
        rtool = self.toolbar.AddTool(13, 'twoTool', wx.Bitmap('wrong.png'), shortHelp ="Simple Tool2")
        stool = self.toolbar.AddTool(14, 'twoTool', wx.Bitmap('wrong.png'), shortHelp ="Simple Tool")

        self.toolbar.Realize()
        self.SetSize((350, 250))
        self.SetTitle('Control')
        self.Centre()

        # print tool bitmap size
        print(self.toolbar.GetToolBitmapSize())

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
(32, 32)
```

**代码示例 2:**

## 蟒蛇 3

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
        rtool = self.toolbar.AddTool(13, 'twoTool', wx.Bitmap('user.png'), shortHelp ="Simple Tool2")

        self.toolbar.Realize()
        self.SetSize((350, 250))
        self.SetTitle('Control')
        self.Centre()

        # print tool bitmap size
        print(self.toolbar.GetToolBitmapSize())

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
(24, 24)
```