# wx 中的 wxPython | DeleteToolByPos()函数。工具栏

> 原文:[https://www . geesforgeks . org/wxpython-delete toolby pos-function-in-wx-toolbar/](https://www.geeksforgeeks.org/wxpython-deletetoolbypos-function-in-wx-toolbar/)

在本文中，我们将了解 wx 的 DeleteToolByPos()函数。wxPython 的工具栏类。DeleteToolByPos()从工具栏中删除指定的工具并删除它。DeleteTool()和 DeleteToolByPos()函数的唯一区别是 DeleteToolByPos()通过其索引指定工具。

> **语法:**wx . toolbar . deletetoolbyPos(self，pos)
> 
> **如果工具被删除，则返回:**真，否则返回假。
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 刷卡机 | （同 Internationalorganizations）国际组织 | 工具的位置从 0 开始。 |

**示例:**

```
import wx

class Example(wx.Frame):
    global count
    count = 0;
    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)

        self.InitUI()

    def InitUI(self):
        pnl = wx.Panel(self)
        self.toolbar = self.CreateToolBar()
        self.ptool = self.toolbar.AddTool(12,
                                          'oneTool',
                                          wx.Bitmap('path / wxPython / right.png'),
                                          shortHelp ="Simple Tool")

        self.ptool = self.toolbar.AddTool(13,
                                          'oneTool',
                                          wx.Bitmap('path / wxPython / wrong.png'),
                                          shortHelp ="Simple Tool")

        self.btn = wx.Button(pnl,
                             label ='Delete',
                             pos =(20, 20))

        self.btn.Bind(wx.EVT_BUTTON, self.Onclick)
        self.toolbar.Realize()
        self.SetSize((350, 250))
        self.SetTitle('Control')
        self.Centre()

    def Onclick(self, e):
        # delete tool using DeleteTool() function
        self.toolbar.DeleteToolByPos(0)

def main():

    app = wx.App()
    ex = Example(None)
    ex.Show()
    app.MainLoop()

if __name__ == '__main__':
    main()
```

**输出:**
*启动应用:*
![](img/af5d34b1a95b7f713c2dc21620877e70.png)

*点击按钮:*
![](img/642837402073cb77931071122f66810a.png)