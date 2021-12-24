# wx Tyson–wx 中的 Check()函数。菜单项

> 原文:[https://www . geesforgeks . org/wxpython-check-function-in-wx-menuitem/](https://www.geeksforgeeks.org/wxpython-check-function-in-wx-menuitem/)

在本文中，我们将学习与 wx 相关的 Check 函数。wxPython 的 MenuItem 类。顾名思义，Check()函数检查或取消检查菜单项(ITEM_CKECK)。请注意，这仅在项目已经附加到菜单时有效。

> **语法:** wx。菜单项。检查(自我，检查=真)
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 支票 | 弯曲件 | 如果选中则设置为真，否则设置为假。 |

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
        self.item = wx.MenuItem(self.fileMenu, 1, '&Check', kind = wx.ITEM_CHECK)
        self.fileMenu.Append(self.item)

        # Check function checks the item at the first place you open the app
        self.item.Check(check = True)
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
![](img/b0a4e9bbe8bda98d7df4f43d7c1fb16f.png)