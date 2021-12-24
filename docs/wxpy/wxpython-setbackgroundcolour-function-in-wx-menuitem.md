# wx Tyson–wx 中的 SetBackgroundColour()函数。菜单项

> 原文:[https://www . geeksforgeeks . org/wxpython-setbackground color-function-in-wx-menuitem/](https://www.geeksforgeeks.org/wxpython-setbackgroundcolour-function-in-wx-menuitem/)

在本文中，我们将学习与 wx 相关的 SetBackgroundColour()函数。wxPython 的 MenuItem 类。SetBackgroundColour()函数只是设置与菜单项相关的背景颜色。
setbackgroundcolor()函数中不需要参数。

> **语法:**
> 
> ```
> wx.MenuItem.SetBackgroundColour(self)
> 
> ```
> 
> **参数:**
> 
> ```
> No parameters are required in SetBackgroundColour() function.
> 
> ```
> 
> **返回类型:**
> 
> ```
> wx.Colour
> 
> ```

**代码示例:**

```
import wx

class Example(wx.Frame):

    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)

        self.InitUI()

    def InitUI(self):
        self.locale = wx.Locale(wx.LANGUAGE_ENGLISH)
        self.menubar = wx.MenuBar()
        self.fileMenu = wx.Menu()
        self.item = wx.MenuItem(self.fileMenu, 1, '&Radio', helpString ="Check Help")
        # set background colour of menu item
        self.item.SetBackgroundColour((100, 155, 139, 255))
        self.st = wx.StaticText(self, label ="", pos =(200, 200))
        self.fileMenu.Append(self.item)
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
![](img/8767b1cb0d64c238f924624aa0cef39d.png)