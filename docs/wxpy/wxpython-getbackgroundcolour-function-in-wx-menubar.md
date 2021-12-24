# wx xpython–wx 中的 GetBackgroundColour()函数。菜单栏

> 原文:[https://www . geesforgeks . org/wxpython-getbackground color-function-in-wx-menu bar/](https://www.geeksforgeeks.org/wxpython-getbackgroundcolour-function-in-wx-menubar/)

在本文中，我们将学习与 wx 相关联的 GetBackgroundColour()函数。wxPython 的菜单栏类。顾名思义，GetBackgroundColour()返回与菜单项相关联的背景颜色。函数没有参数。

> **语法:** wx。菜单栏.获取背景颜色(自身)
> 
> **参数:**getbackground color()函数中不需要参数
> 
> **返回类型:** wx。颜色

**Code Example 1:**

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
        self.item = wx.MenuItem(self.fileMenu, 1, '&Check')
        self.fileMenu.Append(self.item)

        # print the background colour of menu item
        print(self.item.GetBackgroundColour())
        self.menubar.Append(self.fileMenu, '&File')
        self.SetMenuBar(self.menubar)

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
(-1, -1, -1, 255)

```

**代码示例 2:**

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
        self.item = wx.MenuItem(self.fileMenu, 1, '&Check')
        self.item.SetBackgroundColour((225, 200, 100, 255))
        self.fileMenu.Append(self.item)

        # print the background colour of menu item
        print(self.item.GetBackgroundColour())
        self.menubar.Append(self.fileMenu, '&File')
        self.SetMenuBar(self.menubar)

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
(225, 200, 100, 255)

```