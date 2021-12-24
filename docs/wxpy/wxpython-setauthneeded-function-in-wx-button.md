# wx Tyson–wx 中的 SetAuthNeeded()函数。按钮

> 原文:[https://www . geeksforgeeks . org/wxpython-setauthrequired-function-in-wx-button/](https://www.geeksforgeeks.org/wxpython-setauthneeded-function-in-wx-button/)

在本文中，我们将了解与 wx 相关联的 SetAuthNeeded()函数。wxPython 的按钮类。SetAuthNeeded()函数用于设置按钮上是否应该显示需要认证的符号。

它只接受布尔参数，即需要与否。

> **语法:** wx。按钮。设置所需(自身，所需=真)
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 需要 | 弯曲件 | 需要时为真，不需要时为假。 |
> 
> **返回类型:** bool

**代码示例:**

```py
import wx

class Example(wx.Frame):

    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)

        self.InitUI()

    def InitUI(self):
        self.pnl = wx.Panel(self)
        self.btn = wx.Button(self.pnl, label ='Button', pos =(20, 20))

        # SET NEEDED AS TRUE 
        self.btn.SetAuthNeeded(True)
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
![](img/21eb052fb47fe9ffef175fc2edbbfc36.png)