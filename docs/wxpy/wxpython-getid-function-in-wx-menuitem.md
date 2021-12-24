# wx python–getid()函数中的 wx。MenuItem

> 原文:[https://www . geeksforgeeks . org/wxpython-getid-function-in-wx-menuitem/](https://www.geeksforgeeks.org/wxpython-getid-function-in-wx-menuitem/)

在本文中，我们将学习与 wx 相关联的 GetId()函数。wxPython 的 MenuItem 类。顾名思义，GetId()函数返回 int 类型的菜单项标识符。
GetId()函数中不需要参数。

> **语法:**
> 
> ```py
> wx.MenuItem.GetId()
> ```
> 
> **参数:**
> 
> ```py
> No parameters are required in GetId function.
> ```
> 
> **返回类型:**
> 
> ```py
> int
> ```

**代码示例:**

## 蟒蛇 3

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
        self.item = wx.MenuItem(self.fileMenu, 1, '&Check', helpString ="Check Help")
        self.item.SetBitmap(wx.Bitmap('right.png'))
        self.fileMenu.Append(self.item)
        self.menubar.Append(self.fileMenu, '&File')
        self.SetMenuBar(self.menubar)
        # help string associated with menuitem
        id = self.item.GetId()
        # print help string
        print(id)
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
1
```