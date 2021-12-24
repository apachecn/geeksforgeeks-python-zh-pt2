# wx 中的 wxPython–GetLabel()函数。按钮

> 原文:[https://www . geesforgeks . org/wxpython-getlabel-function-in-wx-button/](https://www.geeksforgeeks.org/wxpython-getlabel-function-in-wx-button/)

在本文中，我们将了解与 wx 相关联的 GetLabel()函数。wxPython 的按钮类。GetLabel()函数用于返回按钮的字符串标签。GetLabel()函数不需要任何参数。

> **语法:** wx。按钮。获取标签(自身)
> 
> **参数:**GetLabel()函数不需要参数。
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
        self.pnl = wx.Panel(self)
        self.btn = wx.Button(self.pnl, label ='Button', 
                              pos =(20, 20), size =(100, 20))

        # GET STRING LABEL ON BUTTON
        s = self.btn.GetLabel()
        # PRINT STRING LABEL
        print(s)

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

**控制台输出:**

```
Button

```

**输出窗口:**
![](img/74eea21532d58564f73ad41fa0386976.png)