# wx xpython | wx 中的 SetMarginWidth()函数。菜单项

> 原文:[https://www . geesforgeks . org/wxpython-setmarginwidth-function-in-wx-menuitem/](https://www.geeksforgeeks.org/wxpython-setmarginwidth-function-in-wx-menuitem/)

在本文中，我们将学习与 wx 相关联的 SetMarginWidth()函数。wxPython 的 MenuItem 类。函数的作用是:设置菜单项勾号位图的宽度。

它只接受整数参数，即宽度。

> **语法:**
> 
> ```py
> wx.MenuItem.SetMarginWidth(self, width)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 宽度 | （同 Internationalorganizations）国际组织 | 与勾号关联的宽度。 |

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
        self.st = wx.StaticText(self, label ="", pos =(20, 20),
                                          style = wx.ALIGN_LEFT)
        self.item = wx.MenuItem(self.fileMenu, 1, '&Radio', 
                                       kind = wx.ITEM_CHECK)

        self.fileMenu.Append(self.item)
        self.item.SetMarginWidth(15)
        print(self.item.GetMarginWidth())

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
15
```

![](img/e26c7a9ca43a07802515ab34685b796e.png)