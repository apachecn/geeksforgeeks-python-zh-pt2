# wx 中的 wxPython–GetHelpString()函数。菜单栏

> 原文:[https://www . geesforgeks . org/wxpython-gethelpsring-function-in-wx-menu bar/](https://www.geeksforgeeks.org/wxpython-gethelpstring-function-in-wx-menubar/)

正如我们对 SetHelpString()的了解，在本文中，我们将学习 wx 中的一个重要的 GetHelpString()函数。wxPython 的菜单栏类。SetHelpString()将帮助字符串与 menuitem 相关联，而 GetHelpString()函数返回与菜单项相关联的帮助字符串。

> **语法:**
> 
> ```
> wx.MenuBar.GetHelpString(id)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 身份证明（identification） | （同 Internationalorganizations）国际组织 | “项目标识符”菜单。 |
> 
> **返回:**如果没有帮助字符串或菜单项，则没有找到帮助字符串或空字符串。

**代码示例:**

```
import wx

class Example(wx.Frame):

    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)

        self.InitUI()

    def InitUI(self):
        # create MenuBar using MenuBar() function
        menubar = wx.MenuBar()

        # add menu to MenuBar
        fm1 = wx.Menu()
        fileitem = fm1.Append(20, "Item # 1")
        menubar.Append(fm1, '&Menu # 1')
        self.SetMenuBar(menubar)
        self.SetSize((300, 200))
        self.SetTitle('Menu Bar')
        menubar.SetHelpString(20, "Help String")

        st = wx.StaticText(self, label ="click Item # 1 in Menu # 1")

        # get and print helpstring using SetHelpString() function
        print(menubar.GetHelpString(20))

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
Help String

```