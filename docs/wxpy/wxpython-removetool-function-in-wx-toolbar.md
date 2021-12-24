# wx 中的 wxPython | RemoveTool()函数。工具栏

> 原文:[https://www . geesforgeks . org/wxpython-remove tool-function-in-wx-toolbar/](https://www.geeksforgeeks.org/wxpython-removetool-function-in-wx-toolbar/)

在本文中，我们将了解与 wx 相关联的 RemoveTool()函数。wxPython 的工具栏类。RemoveTool()从工具栏中删除给定的工具，但不删除它。这允许稍后将此工具插入/添加回此(或另一)工具栏。RemoveTool()只将 id 作为参数。

> **语法:**
> 
> ```py
> wx.ToolBar.RemoveTool(self, id)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 身份证明（identification） | （同 Internationalorganizations）国际组织 | 传递给添加工具的有问题工具的标识。 |
> 
> **返回类型:**
> 
> ```py
> wx.ToolBarToolBase
> 
> ```

**代码示例 1:**

```py
import wx

class Example(wx.Frame):

    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)
        self.InitUI()

    def InitUI(self):
        self.locale = wx.Locale(wx.LANGUAGE_ENGLISH)
        self.toolbar = self.CreateToolBar()
        td = self.toolbar.AddTool(1, '', wx.Bitmap('wrong.png'))
        te = self.toolbar.AddTool(2, '', wx.Bitmap('right.png'))
        tf = self.toolbar.AddTool(3, '', wx.Bitmap('sep.png'))
        self.toolbar.Realize()
        self.Bind(wx.EVT_TOOL, self.OnOne, td)

        self.SetSize((350, 250))
        self.SetTitle('Undo redo')
        self.Centre()

    def OnOne(self, e):
        # delete tools from toolbar using RemoveTool() function
        self.toolbar.RemoveTool(id = 2)
        self.toolbar.RemoveTool(id = 3)
        # Realize() called to finalize new added tools
        self.toolbar.Realize()

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
*点击前交叉工具:*
![](img/013612b36866154b59c9d4d8118cf9ca.png)

*点击十字工具后:*
![](img/707b3ab9d987ed5d4872b084d49a26bc.png)