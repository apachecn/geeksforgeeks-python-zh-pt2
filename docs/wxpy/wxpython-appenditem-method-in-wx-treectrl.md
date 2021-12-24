# wx 中的 wxPython–AppendItem()方法。TreeCtrl

> 原文:[https://www . geesforgeks . org/wxpython-appenditem-method-in-wx-tree ctrl/](https://www.geeksforgeeks.org/wxpython-appenditem-method-in-wx-treectrl/)

在本文中，我们将学习 wx 中的 AppendItem()方法。wxPython 的 TreeCtrl 类。AppendItem()方法用于将一个项追加到由 parent 标识的分支末尾，返回一个新的项 id。

Append()方法采用 parent(wx。作为参数。

> **语法:** wx。TreeCtrl.AppendItem()
> 
> **参数**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 父母 | wx(地名)。TreeItemId(树项目 Id) | 项目的父根。 |
> | 文本 | 线 | 节点上的文本 |
> | 图像 | （同 Internationalorganizations）国际组织 | image 参数是正常图像列表中的一个索引，分别指定未选择项目的图像。 |
> | selImage | （同 Internationalorganizations）国际组织 | selImage 参数是普通图像列表中的一个索引，分别指定所选项目的图像。 |
> | 数据 | treeitemsata | 根项目的数据。 |
> 
> **返回类型:** wx。TreeItemId

**代码示例:**

```py
import wx

class MainFrame(wx.Frame):

    def __init__(self):
        wx.Frame.__init__(self, parent = None, title ='TreeCtrl Demo')
        # tree control
        self.tree = wx.TreeCtrl(self, wx.ID_ANY, wx.DefaultPosition, wx.DefaultSize)

        # add a root node to tree
        self.root = self.tree.AddRoot('Root ')

        # add item to self.root
        self.tree.AppendItem(self.root, "Item")

        # expand tree
        self.tree.Expand(self.root)

        # show frame
        self.Show()

if __name__ == '__main__':
    app = wx.App(redirect = False)
    frame = MainFrame()
    app.MainLoop()
```

**输出窗口:**
![](img/85047c7a168040f6a0c28a2d74cfd770.png)