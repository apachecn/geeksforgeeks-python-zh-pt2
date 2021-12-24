# wx 中的 wxPython–IsCheck()函数。菜单项

> 原文:[https://www . geesforgeks . org/wxpython-ischeck-function-in-wx-menuitem/](https://www.geeksforgeeks.org/wxpython-ischeck-function-in-wx-menuitem/)

在本文中，我们将学习与 wx 相关的 IsCheck()方法。wxPython 的 MenuItem 类。如果项目是检查项目，IsCheck()方法只返回 True，如果项目不是检查项目，则返回 False。
请注意，与 IsCheckable()不同，单选按钮不会返回 True。

> **语法:**
> 
> ```py
> wx.IsCheck(self)
> 
> ```
> 
> **参数:**
> 
> ```py
> No parameters are needed by IsCheck() function.
> 
> ```
> 
> **返回类型:**
> 
> ```py
> bool
> 
> ```

**代码示例:**

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
        self.item = wx.MenuItem(self.fileMenu, 1, '&Check', helpString ="Check Help", kind = wx.ITEM_CHECK)
        self.item.SetBitmap(wx.Bitmap('right.png'))
        self.item.SetTextColour((79, 81, 230, 255))
        self.st = wx.StaticText(self, label ="", pos =(200, 200))
        self.fileMenu.Append(self.item)
        self.menubar.Append(self.fileMenu, '&File')
        self.SetMenuBar(self.menubar)
        # label of menu item
        clr = self.item.GetTextColour()
        # print label of menuitem
        if self.item.IsCheck()== True:
            print("Item is check")
        else:
            print("Item is not check")
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
Item is Check

```

**输出窗口:**
![](img/e31dea6586f26ecba02e44aa970174f4.png)