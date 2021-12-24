# wxPython–wx 中的 Create()函数。按钮

> 原文:[https://www . geesforgeks . org/wxpython-create-function-in-wx-button/](https://www.geeksforgeeks.org/wxpython-create-function-in-wx-button/)

在本文中，我们将了解与 wx 相关联的 Clear()函数。wxPython 的按钮类。Create()函数用于两步创建的按钮创建函数。

它将按钮的属性作为参数。

> **语法:** wx。按钮. Create(self，parent，id=ID_ANY，label= "，pos=DefaultPosition，size=DefaultSize，style=0，validator=DefaultValidator，name=ButtonNameStr)
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 父母 | wx。窗户 | 父窗口。不应该是无。 |
> | 身份证明（identification） | wx.窗口标识 | 控件标识符。值-1 表示默认值。 |
> | 标签 | 线 | 标示文字。 |
> | 刷卡机 | wx。要点 | 窗口位置。 |
> | 大小 | wx。窗户 | 窗口大小。 |
> | 风格 | 长的 | 窗口样式。 |
> | 验证器 | wx。验证器 | 窗口验证器。 |
> | 名字 | 线 | 窗口名称。 |
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
        self.btn = wx.Button()

        # CREATE BUTTON USING Create() function FOR TWO STEP CREATION
        self.btn.Create(self.pnl, label ='Button', pos =(20, 20))

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
![](img/74eea21532d58564f73ad41fa0386976.png)