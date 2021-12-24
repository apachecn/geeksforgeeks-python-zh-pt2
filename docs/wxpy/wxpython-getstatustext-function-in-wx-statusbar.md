# wx 中的 wxPython–GetStatusText()函数。状态栏

> 原文:[https://www . geesforgeks . org/wxpython-getstatustext-function-in-wx-status bar/](https://www.geeksforgeeks.org/wxpython-getstatustext-function-in-wx-statusbar/)

在本文中，我们将了解与 wx 相关联的 GetStatusText()函数。wxPython 的 StatusBar 类。GetStatusText()函数是 wx 中最有用的方法之一。StatusBar 作为该函数返回与状态栏字段相关联的字符串。
只需要一个参数状态字段的编号就可以检索，从零开始。

> **语法：** wx.StatusBar.GetStatusText（self， i=0）
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 我 | （同 Internationalorganizations）国际组织 | 要检索的状态字段的编号，从零开始。 |
> 
> **如果字段有效，则返回:**状态字段字符串，否则返回空字符串。
> 
> **返回类型:**字符串

**代码示例:**

```
import wx

class Example(wx.Frame):

    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)

        self.InitUI()

    def InitUI(self):

        self.locale = wx.Locale(wx.LANGUAGE_ENGLISH)
        self.statusbar = wx.StatusBar()
        self.statusbar.Create(self, id = 1, style = wx.STB_DEFAULT_STYLE, 
                                                    name = "Status Bar")

        self.SetStatusBar(self.statusbar)
        self.SetSize((350, 250))
        self.statusbar.SetFieldsCount(2)
        self.statusbar.SetStatusWidths([150, 150])
        self.statusbar.SetStatusText("This is first field", 0)
        self.statusbar.SetStatusText("This is second field", 1)
        self.statusbar.SetStatusStyles(styles =[wx.SB_RAISED, wx.SB_SUNKEN])

        # PRINT STATUS TEXT OF TWO FIELDS
        print("First Field Text: "+self.statusbar.GetStatusText(0))
        print("Second Field Text: "+self.statusbar.GetStatusText(1))
        self.SetTitle('New Frame Title')
        self.Centre()

def main():
    app = wx.App()
    ex = Example(None)
    ex.Show()
    app.MainLoop()

if __name__ == '__main__':
    main()
```

**控制台输出:**

```
First Field Text: This is first field
Second Field Text: This is second field

```

**输出窗口:**
![](img/b769397b1f598e7432d07884b788e142.png)