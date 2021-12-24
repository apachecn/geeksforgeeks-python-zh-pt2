# python 中的 wxPython | GetToolPos()函数

> 原文:[https://www . geesforgeks . org/wxpython-gettoolpos-function-in-python/](https://www.geeksforgeeks.org/wxpython-gettoolpos-function-in-python/)

在本文中，我们将了解与 wx 相关联的 GetToolPos()函数。wxPython 的工具栏类。GetToolPos()函数只是返回工具在工具栏中的位置，如果找不到工具，则返回 NOT_FOUND。GetToolPos()函数只接受参数中的 tooId(有问题的工具的 Id，传递给 AddTool)。

> **语法:**
> 
> ```py
> wx.ToolBar.GetToolPos(self, toolId)
> ```
> 
> **参数:**
> 
> <figure class="table">
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 椅子 | （同 Internationalorganizations）国际组织 | 传递给添加工具的有问题工具的标识。 |
> 
> </figure>
> 
> **返回:**
> 返回刀具在工具栏中的位置，从 0 开始。
> **返回类型**
> 
> ```py
> int
> ```

**代码示例 1:**

## 蟒蛇 3

```py
import wx

class Example(wx.Frame):
    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)
        self.InitUI()

    def InitUI(self):
        self.locale = wx.Locale(wx.LANGUAGE_ENGLISH)
        pnl = wx.Panel(self)
        self.toolbar = self.CreateToolBar()
        # Add Tools Using AddTool function
        rtool = self.toolbar.AddLabelTool(id = 13, label = "Tool one", bitmap = wx.Bitmap('right.png'), shortHelp ="short help 1", longHelp = "Long help associated with simple tool 1")
        stool = self.toolbar.AddLabelTool(id = 14, label = "Tool two", bitmap = wx.Bitmap('wrong.png'), shortHelp ="short help 2", longHelp = "Long help associated with simple tool 2")

        self.toolbar.Realize()
        self.SetSize((350, 250))
        self.SetTitle('Control')
        self.Centre()
        # variable bl storing position of tool
        bl = self.toolbar.GetToolPos(14)

        # print tool position value
        print(bl)

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
1
```

**代码示例 2:**

## 蟒蛇 3

```py
import wx

class Example(wx.Frame):
    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)
        self.InitUI()

    def InitUI(self):
        self.locale = wx.Locale(wx.LANGUAGE_ENGLISH)
        pnl = wx.Panel(self)
        self.toolbar = self.CreateToolBar()
        # Add Tools Using AddTool function
        rtool = self.toolbar.AddLabelTool(id = 13, label = "Tool one", bitmap = wx.Bitmap('right.png'), shortHelp ="short help 1", longHelp = "Long help associated with simple tool 1")
        stool = self.toolbar.AddLabelTool(id = 14, label = "Tool two", bitmap = wx.Bitmap('wrong.png'), shortHelp ="short help 2", longHelp = "Long help associated with simple tool 2")

        self.toolbar.Realize()
        self.SetSize((350, 250))
        self.SetTitle('Control')
        self.Centre()
        # variable bl storing position of tool
        bl = self.toolbar.GetToolPos(13)

        # print tool position value
        print(bl)

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
0
```