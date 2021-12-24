# wxPython–在 wx 中启用()功能。单选按钮

> 原文:[https://www . geesforgeks . org/wxpython-enable-function-in-wx-radio button/](https://www.geeksforgeeks.org/wxpython-enable-function-in-wx-radiobutton/)

在本文中，我们将了解与 wx 相关联的 Enable()函数。wxPython 的 RadioButton 类。Enable()功能仅用于启用或禁用用户输入的单选按钮。它采用布尔参数“真”来启用，而“假”来禁用。

> **语法:** wx。单选按钮。启用(自身，启用=真)
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 使能够 | 弯曲件 | 如果为真，则启用输入窗口。如果为假，则禁用窗口。 |
> 
> **返回类型:** bool
> 
> **返回:**如果窗口已启用或禁用，则为真；如果未执行任何操作，即窗口已处于指定状态，则为假。

**代码示例:**

```
import wx

APP_EXIT = 1

class Example(wx.Frame):

    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)

        self.InitUI()

    def InitUI(self):
        self.pnl = wx.Panel(self)

        # create radio button at position (30, 10)
        self.rb1 = wx.RadioButton(self.pnl, label ='Btn1', 
                             pos =(30, 10), size =(100, 20))

        # disable the radio button using Enable() function
        self.rb1.Enable(False)

def main():
    app = wx.App()
    ex = Example(None)
    ex.Show()
    app.MainLoop()

if __name__ == '__main__':
    main()
```

![](img/0f8963d0310250f2ab83c79ab890788a.png)