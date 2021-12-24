# wxPython–getmarginwinidth(wx 中的 0 函数。菜单项

> 原文:[https://www . geeksforgeeks . org/wxpython-getmarginwidth0-function-in-wx-menuitem/](https://www.geeksforgeeks.org/wxpython-getmarginwidth0-function-in-wx-menuitem/)

在本文中，我们将学习与 wx 相关联的 GetMarginWidth()函数。wxPython 的 MenuItem 类。获取菜单项勾号位图的宽度。GetMarginWidth()函数不接受任何参数。

> **语法:**
> 
> ```py
> wx.MenuItem.GetMarginWidth(self)
> 
> ```
> 
> **参数:**
> 
> ```py
> No parameters are required in GetMarginWidth().
> 
> ```
> 
> **返回类型:**
> 
> ```py
> int
> 
> ```

**代码示例 1:**

```py
import wx

class Example(wx.Frame):

    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)

        self.InitUI()

    def InitUI(self):
        self.locale = wx.Locale(wx.LANGUAGE_ENGLISH)

        self.menubar = wx.MenuBar()
        self.fileMenu = wx.Menu()
        self.item = wx.MenuItem(self.fileMenu, 1, '&Check\tCtrl + c', helpString ="Check Help")
        self.fileMenu.Append(self.item)
        self.menubar.Append(self.fileMenu, '&File')
        self.SetMenuBar(self.menubar)
        # print margin width
        margin = self.item.GetMarginWidth()
        print(margin)
        self.SetSize((350, 250))
        self.SetTitle('Icons and shortcuts')
        self.Centre()

def main():
    app = wx.App()
    ex = Example(None)
    ex.Show()
    app.MainLoop()

if __name__ == '__main__':
    main()
```

**输出:**
默认边距宽度

```py
3

```

**代码示例 1:**

```py
import wx

class Example(wx.Frame):

    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)

        self.InitUI()

    def InitUI(self):
        self.locale = wx.Locale(wx.LANGUAGE_ENGLISH)

        self.menubar = wx.MenuBar()
        self.fileMenu = wx.Menu()
        self.item = wx.MenuItem(self.fileMenu, 1, '&Check\tCtrl + c', helpString ="Check Help")
        self.item.SetMarginWidth(12)
        self.fileMenu.Append(self.item)
        self.menubar.Append(self.fileMenu, '&File')
        self.SetMenuBar(self.menubar)
        # print margin width
        margin = self.item.GetMarginWidth()
        print(margin)
        self.SetSize((350, 250))
        self.SetTitle('Icons and shortcuts')
        self.Centre()

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