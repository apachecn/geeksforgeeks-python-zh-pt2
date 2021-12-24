# wx xpython–wx 中的 IsChecked()函数。菜单栏

> 原文:[https://www . geeksforgeeks . org/wxpython-ischecked-function-in-wx-menu bar/](https://www.geeksforgeeks.org/wxpython-ischecked-function-in-wx-menubar/)

在本文中，我们将学习与 wx 相关联的 IsChecked()函数。wxPython 的菜单栏类。IsChecked()函数只是确定一个项目是否被选中。如果找到并检查了该项，则函数返回真，否则返回假。
IsChecked()函数以 id 为自变量。

> **语法:** wx。菜单栏. IsChecked(自身，id)
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 身份证明（identification） | （同 Internationalorganizations）国际组织 | 菜单项标识符。 |

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
        self.fileMenu2 = wx.Menu()
        self.item = wx.MenuItem(self.fileMenu, 1, '&Check', helpString ="Check Help", 
                                                               kind = wx.ITEM_CHECK)
        self.item.SetBitmap(wx.Bitmap('right.png'))
        self.fileMenu.Append(self.item)
        self.menubar.Append(self.fileMenu, '&File')
        self.Bind(wx.EVT_MENU, self.Onclick, self.item)
        self.SetMenuBar(self.menubar)
        self.SetSize((350, 250))
        self.SetTitle('New Frame Title')
        self.Centre()

    def Onclick(self, e):
        if(self.menubar.IsChecked(1)== True):
            # print CHECKED if True
            print("CHECKED")
        else:
            # else print UNCHECKED
            print("UNCHECKED")

def main():
    app = wx.App()
    ex = Example(None)
    ex.Show()
    app.MainLoop()

if __name__ == '__main__':
    main()
```

**输出窗口:**

![](img/63765dbfe4788ccf43d51d11c11822e5.png)

![](img/f438a2eedcb224c807c0b5b4ff8d86c5.png)

**控制台输出:**

```
CHECKED
UNCHECKED

```