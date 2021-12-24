# wx Tyson–wx 中的 GetClassDefaultAttributes()函数。按钮

> 原文:[https://www . geesforgeks . org/wxpython-getclassdefaultattributes-function-in-wx-button/](https://www.geeksforgeeks.org/wxpython-getclassdefaultattributes-function-in-wx-button/)

在本文中，我们将了解与 wx 相关联的 GetClassDefaultAttributes()函数。wxPython 的按钮类。GetClassDefaultAttributes()函数用于返回 wx。VisualAttributes 对象，用于背景色、前景色和字体等属性。
它以变式作为论证论据。

> **语法:** wx。
> **参数:**
> 
> <figure class="table">
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 不同的 | WindowVariant | 按钮的变体。 |
> 
> </figure>
> 
> **返回类型:** wx。视觉属性

**代码示例:**

## 蟒蛇 3

```py
import wx

class Example(wx.Frame):

    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)

        self.InitUI()

    def InitUI(self):
        self.pnl = wx.Panel(self)
        self.btn = wx.Button(self.pnl, label ='Button', pos =(20, 20))

        # wx.VisualAttributes OBJECT
        va = self.btn.GetClassDefaultAttributes(variant = wx.WINDOW_VARIANT_NORMAL)

        # PRINT PROPERTIES
        print(va.colBg)
        print(va.colFg)
        print(va.font)

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

```py
(240, 240, 240, 255)
(0, 0, 0, 255)
```

**输出窗口:**

![](img/74eea21532d58564f73ad41fa0386976.png)