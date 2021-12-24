# wx Tyson–wx 中的 GetStatusWidth()函数。状态栏

> 原文:[https://www . geesforgeks . org/wxpython-getstatuswith-function-in-wx-status bar/](https://www.geeksforgeeks.org/wxpython-getstatuswidth-function-in-wx-statusbar/)

在本文中，我们将了解与 wx 相关联的 GetStatusWidth()函数。wxPython 的 StatusBar 类。GetStatusWidth()函数只是用来返回第 n 个字段的宽度。它只将字段的索引(位置)作为参数。

> **语法:**wx . status bar . get status width(self，n)
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | n | （同 Internationalorganizations）国际组织 | 状态字段的位置。 |
> 
> **返回类型:** int

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

        # PRINT WIDTHS OF TWO FIELDS
        print("First Field Width: "+str(self.statusbar.GetStatusWidth(0)))
        print("Second Field Width: "+str(self.statusbar.GetStatusWidth(1)))
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
First Field Width: 150
Second Field Width: 150

```

**输出窗口:**
![](img/8c94066e9669970e16093f2946851c9c.png)