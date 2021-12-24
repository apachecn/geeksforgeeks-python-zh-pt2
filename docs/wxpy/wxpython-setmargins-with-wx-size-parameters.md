# wxPython–带 wx 的 SetMargins()。尺寸参数

> 原文:[https://www . geesforgeks . org/wxpython-setmargins-with-wx-size-parameters/](https://www.geeksforgeeks.org/wxpython-setmargins-with-wx-size-parameters/)

在本文中，我们将学习与 wx 相关的 SetMargins()函数。wxPython 的工具栏类。与上一篇文章类似，SetMargins()函数为工具栏设置边距。但唯一的区别是，取两个不同的参数 x 和 y，取一个 wx。尺寸参数。

> **语法:**
> 
> ```py
> wx.ToolBar.SetMargind(self, size)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 大小 | wx。大小 | 边距大小。 |
> 
> **返回类型:** wx。工具栏工具库

**代码示例:**

```py
import wx

class Example(wx.Frame):

    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)
        self.InitUI()

    def InitUI(self):
        self.locale = wx.Locale(wx.LANGUAGE_ENGLISH)
        self.toolbar = self.CreateToolBar()
        # set margins with size parameter
        self.toolbar.SetMargins(size =(30, 25))
        td = self.toolbar.AddTool(1, 'right', wx.Bitmap('right.png'))
        self.toolbar.Realize()
        # print margins
        print(self.toolbar.GetMargins())
        self.SetSize((350, 250))
        self.SetTitle('Undo redo')
        self.Centre()

    def OnQuit(self, e):

        self.Close()

def main():

    app = wx.App()
    ex = Example(None)
    ex.Show()
    app.MainLoop()

if __name__ == '__main__':
    main()
```

**输出:**

```py
(30, 25)

```