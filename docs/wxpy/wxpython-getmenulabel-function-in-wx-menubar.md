# wx Tyson–wx 中的 GetMenuLabel()函数。菜单栏

> 原文:[https://www . geesforgeks . org/wxpython-getmenulabel-function-in-wx-menubar/](https://www.geeksforgeeks.org/wxpython-getmenulabel-function-in-wx-menubar/)

GetMenuLabel()函数是 wx 中存在的另一个函数。wxPython 的菜单栏类。函数的作用是:返回菜单栏中菜单的标签。GetMenuLabel()只获取菜单栏中菜单的位置。

> **语法:**
> 
> ```py
> wx.MenuBar.GetMenuLabel(self, menuindex)
> ```
> 
> **参数:**
> 
> <figure class="table">
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 刷卡机 | （同 Internationalorganizations）国际组织 | 菜单栏上菜单的位置，从零开始。 |
> 
> </figure>
> 
> **返回:**菜单标签，如果没有找到菜单，则返回空字符串。

**代码示例:**

## 蟒蛇 3

```py
import wx

class Example(wx.Frame):

    def __init__(self, *args, **kw):
        super(Example, self).__init__(*args, **kw)

        # create MenuBar using MenuBar() function
        menubar = wx.MenuBar()

        # add menu to MenuBar
        fm1 = wx.Menu()
        fileitem = fm1.Append(20, "one")

        fm2 = wx.Menu()
        fileitem2 = fm2.Append(21, "two")
        menubar.Append(fm1, '&Menu_one')
        menubar.Append(fm2, '&Menu_two')
        self.SetMenuBar(menubar)
        self.SetSize((300, 200))
        self.SetTitle('Menu Bar')

        # STATIC TEXT WITH LABEL OF MENU AT POSITION 1
        st1 = wx.StaticText(self, label = menubar.GetMenuLabel(1),
                                            style = wx.ALIGN_LEFT)

def main():
    app = wx.App()
    ex = Example(None)
    ex.Show()
    app.MainLoop()

if __name__ == '__main__':
    main()
```

**窗口:**

![](img/42272fa5653f9f9cd70e649c02d25726.png)