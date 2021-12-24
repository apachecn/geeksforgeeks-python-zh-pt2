# wx python–get font()函数在 wx 中。MenuItem

> 哎哎哎:# t0]https://www . geeksforgeeks . org/wx python-getfont-function-in-wx-menu item/

在本文中，我们将学习与 wx 相关联的 GetFont()函数。wxPython 的 MenuItem 类。GetFont()函数用于简单地返回与菜单项关联的字体。
GetFont()函数不需要参数。

> **语法:**
> 
> ```py
> wx.MenuItem.GetFont(self)
> ```
> 
> **参数:**
> 
> ```py
> no parameters are required in GetFont() function.
> ```
> 
> **返回类型:**
> 
> ```py
> wx.Font 
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
        self.item = wx.MenuItem(self.fileMenu, 1, '&Check')
        self.item.SetBitmap(wx.Bitmap('right.png'))
        self.fileMenu.Append(self.item)
        self.menubar.Append(self.fileMenu, '&File')
        self.SetMenuBar(self.menubar)
        f = self.item.GetFont();
        print(f.GetFamily)
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
<built-in method GetFamily of Font object at 0x000000AD0C9A4430>
```

默认字体