# wx xpython–wx 中的 GetDefaultSize()函数。按钮

> 原文:[https://www . geesforgeks . org/wxpython-getdefaultsize-function-in-wx-button/](https://www.geeksforgeeks.org/wxpython-getdefaultsize-function-in-wx-button/)

在本文中，我们将了解与 wx 相关联的 GetDefaultSize()函数。wxPython 的按钮类。函数的作用是:返回按钮的默认大小。

建议使所有对话框按钮的大小相同，该功能允许检索最适合的(平台和当前字体相关的)大小。

> **语法:** wx。按钮。获取默认值大小(win =无)
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 胜利 | wx。窗户 | 父窗口。 |
> 
> **返回类型:** wx。大小

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

        # GET DEFAULT SIZE
        s = self.btn.GetDefaultSize(self)
        # PRINT DEFAULT SIZE
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
(88, 26)

```

**输出窗口:**
![](img/74eea21532d58564f73ad41fa0386976.png)