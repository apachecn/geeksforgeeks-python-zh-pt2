# wx Tyson–IsRadio()在 wx 中的功能。菜单项

> 原文:[https://www . geesforgeks . org/wxpython-is radio-function-in-wx-menuitem/](https://www.geeksforgeeks.org/wxpython-isradio-function-in-wx-menuitem/)

在本文中，我们将了解与 wx 相关的 IsRadio 功能。wxPython 的 MenuItem 类。如果项目是单选按钮(项目)，则 IsRadio()函数返回 True。IsRadio()函数仅对无线电项目返回 True，不对检查项目返回 True。
IsRadio()函数不需要参数。

> **语法:**
> 
> ```
> wx.MenuItem.IsRadio(Self)
> ```
> 
> **参数:**
> 
> ```
> No parameters are required by IsRadio() function.
> ```
> 
> **返回类型:**
> 
> ```
> bool
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

        self.menubar = wx.MenuBar()
        self.fileMenu = wx.Menu()
        self.item = wx.MenuItem(self.fileMenu, 1, '&Radio 1', helpString ="Check Help", kind = wx.ITEM_RADIO)
        self.item2 = wx.MenuItem(self.fileMenu, 1, '&Radio 2', helpString ="Check Help", kind = wx.ITEM_RADIO)
        self.item.SetTextColour((79, 81, 230, 255))
        self.item2.SetTextColour((79, 81, 230, 255))
        self.st = wx.StaticText(self, label ="", pos =(200, 200))
        self.fileMenu.Append(self.item)
        self.fileMenu.Append(self.item2)
        self.menubar.Append(self.fileMenu, '&File')
        self.SetMenuBar(self.menubar)

        if self.item.IsRadio()== True:
            # print if item is radio
            print("Item is Radio")
        else:
            # print if item is not radio
            print("Item is not Radio")

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
Item is Radio
```

**输出窗口:**

![](img/42858acf591446d9f56e90105e716291.png)