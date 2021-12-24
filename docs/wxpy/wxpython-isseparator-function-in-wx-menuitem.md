# wx xpython–wx 中的 IsSeparator()函数。菜单项

> 原文:[https://www . geeksforgeeks . org/wxpython-is separator-function-in-wx-menuitem/](https://www.geeksforgeeks.org/wxpython-isseparator-function-in-wx-menuitem/)

在本文中，我们将了解与 wx 相关联的 IsSeparator()函数。wxPython 的 MenuItem 类。如果项目是分隔符，IsSeparator()函数只返回 True。如果一个项目的 id 是 wx，它可以被声明/设置为分隔符。ID_SEPARATOR。
is parator()函数不需要参数。

> **语法:**
> 
> ```
> wx.MenuItem.IsSeparator(self)
> 
> ```
> 
> **参数:**
> 
> ```
> No parameters are required by IsSeparator() function.
> 
> ```
> 
> **返回类型:**
> 
> ```
> bool
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
        self.item = wx.MenuItem(self.fileMenu, wx.ID_SEPARATOR)
        self.item2 = wx.MenuItem(self.fileMenu, 1, '&Radio 2', helpString ="Check Help", kind = wx.ITEM_RADIO)
        self.item2.SetTextColour((79, 81, 230, 255))
        self.st = wx.StaticText(self, label ="", pos =(200, 200))
        self.fileMenu.Append(self.item)
        self.fileMenu.Append(self.item2)
        self.menubar.Append(self.fileMenu, '&File')
        self.SetMenuBar(self.menubar)

        if self.item.IsSeparator()== True:
            # print if item is separator
            print("Item is Separator")
        else:
            # print if item is not separator
            print("Item is not Separator")

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

```
Item is Separator

```

**输出窗口:**
![](img/4d8042c21acb6858ac13da2ceeec3b4c.png)