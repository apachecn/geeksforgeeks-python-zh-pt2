# wxPython–更改按钮的前景色

> 原文:[https://www . geeksforgeeks . org/wxpython-change-前景色-按钮/](https://www.geeksforgeeks.org/wxpython-change-foreground-colour-of-button/)

在本文中，我们将学习如何改变按钮的前景色或按钮的字体颜色。为此，我们将使用与 wx 关联的 SetForegroundColour()函数。wxPython 的按钮类。

SetForegroundColour()函数只是取 wx。前景的颜色参数。

> **语法:** wx。按钮。设置背景颜色(自身，颜色)
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 颜色 | wx。颜色 | 前景的颜色。 |

**代码示例:**

```
import wx

class Example(wx.Frame):

    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)
        self.InitUI()

    def InitUI(self):
        self.locale = wx.Locale(wx.LANGUAGE_ENGLISH)

        # create parent panel for button        
        self.pnl = wx.Panel(self)

        # create button at point (20, 20)
        self.btn = wx.Button(self.pnl, id = 1, label ="Button", pos =(20, 20),
                                            size =(300, 40),  name ="button")

        # change foreground colour of button to blue
        self.btn.SetForegroundColour((0, 0, 255, 255))

        self.SetSize((350, 250))
        self.SetTitle('wx.Button')
        self.Centre()

def main():
    app = wx.App()
    ex = Example(None)
    ex.Show()
    app.MainLoop()

if __name__ == '__main__':
    main()
```

**输出窗口:**
![](img/2f3ce23219f9ba609980e743f93195c9.png)