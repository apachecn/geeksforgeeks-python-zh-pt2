# wx Tyson–wx 中的 Detach()函数。菜单栏

> 原文:[https://www . geesforgeks . org/wxpython-detach-function-in-wx-menu bar/](https://www.geeksforgeeks.org/wxpython-detach-function-in-wx-menubar/)

在本文中，我们将学习与 wx 相关联的 Detach()函数。wxPython 的菜单栏类。分离()函数只是分离与框架关联的菜单栏。

分离()函数不接受参数。

> **语法:** wx。菜单栏。分离(自我)
> 
> **参数:** Detach()函数不接受参数。

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

        self.item = wx.MenuItem(self.fileMenu, 1, '&Check', 
                                    helpString ="Check Help")
        self.item.SetBitmap(wx.Bitmap('right.png'))

        # SET BLUE COLOUR FOR TEXT FORMAT(R, B, G, A)
        self.item.SetTextColour((79, 81, 230, 255))
        self.fileMenu.Append(self.item)
        self.menubar.Append(self.fileMenu, '&File')
        self.menubar.Attach(self)

        # Detach menubar
        self.menubar.Detach()
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
![](img/05c3175bb17b9402fcf8198cb61848b5.png)