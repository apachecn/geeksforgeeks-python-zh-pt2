# wxPython–wx 中的 SetToolNormalBitmap()函数。工具栏

> 原文:[https://www . geesforgeks . org/wxpython-settoolbnormalbitmap-function-in-wx-toolbar/](https://www.geeksforgeeks.org/wxpython-settoolnormalbitmap-function-in-wx-toolbar/)

在本文中，我们将学习与 wx 相关联的 SetToolNormalBitmap()函数。wxPython 的工具栏类。SetToolNormalBitmap()用于设置给定 ID 的工具要使用的位图。这只能在按钮工具上使用，不能在控件上使用。它包含两个参数，即 id 和位图。

> **语法:**
> 
> ```
> wx.ToolBar.SetToolNormalBitmap(self, id, bitmap)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 身份证明（identification） | （同 Internationalorganizations）国际组织 | 传递给添加工具的有问题工具的标识。 |
> | 位图 | wx(地名)。点阵图(Bitmap) | 用于法线工具的位图。 |

**代码示例:**

```
import wx

class Example(wx.Frame):

    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)
        self.InitUI()

    def InitUI(self):
        self.locale = wx.Locale(wx.LANGUAGE_ENGLISH)
        self.toolbar = self.CreateToolBar()

        td = self.toolbar.AddTool(1, 'right', wx.Bitmap('right.png'))
        # set disabled bitmap for tool wit id = 1
        self.toolbar.Realize()
        self.Bind(wx.EVT_TOOL, self.OnOne, td)

        self.SetSize((350, 250))
        self.SetTitle('Undo redo')
        self.Centre()

    def OnOne(self, e):
        # set new bitmap of tool with id = 1
        self.toolbar.SetToolNormalBitmap(id = 1, bitmap = wx.Bitmap('wrong.png'))
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
*点击工具前:*
![](img/7b0d92036fba0855d65e34c8bb93971a.png)

*点击工具后:*
![](img/3b4b687157ec9232042d758c7ae9b4b0.png)