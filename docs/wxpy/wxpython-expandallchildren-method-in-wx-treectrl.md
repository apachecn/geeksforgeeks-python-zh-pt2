# wx xpython–wx 中的 ExpandAllChildren()方法。TreeCtrl

> 原文:[https://www . geeksforgeeks . org/wxpython-expandalchilds-method-in-wx-tree ctrl/](https://www.geeksforgeeks.org/wxpython-expandallchildren-method-in-wx-treectrl/)

在本文中，我们将学习与 wx 相关联的 ExpandAllChildren()方法。wxPython 的 TreeCtrl 类。ExpandAllChildren()方法用于展开在方法中作为参数传递的特定项下的所有节点。基本上，这个方法递归地扩展给定的项目及其所有子项目。

这个函数将树节点项作为一个参数，我们希望递归地扩展到这个参数。

> **语法:** wx。扩展子对象(自身，项目)

**参数:**

<figure class="table">

| **参数** | **类型** | **描述** |
| 项目 | wx(地名)。TreeItemId(树项目 Id) | 我们要与 editlabel 关联的项。 |

</figure>

**代码示例:**

## 计算机编程语言

```py
import wx 

class MyTree(wx.TreeCtrl): 

    def __init__(self, parent, id, pos, size, style): 
        wx.TreeCtrl.__init__(self, parent, id, pos, size, style) 

class TreePanel(wx.Panel): 

    def __init__(self, parent): 
        wx.Panel.__init__(self, parent) 

        # create tree control in window 
        self.tree = MyTree(self, wx.ID_ANY, wx.DefaultPosition, 
                           wx.DefaultSize, wx.TR_HAS_BUTTONS) 

        # CREATE TREE ROOT 
        self.root = self.tree.AddRoot('root') 
        self.tree.SetPyData(self.root, ('key', 'value')) 

        # add item to root 
        item = self.tree.AppendItem(self.root, "Item") 
        item2 = self.tree.AppendItem(self.root, "Item") 
        item3 = self.tree.AppendItem(item, "SubItem")
        item4 = self.tree.AppendItem(item, "SubItem")
        item5 = self.tree.AppendItem(item2, "SubItem")
        item6 = self.tree.AppendItem(item, "SubItem")

        # expand root node
        self.tree.Expand(self.root)

        # expand all nodes of the tree
        self.tree.ExpandAllChildren(item) 

        sizer = wx.BoxSizer(wx.VERTICAL) 
        sizer.Add(self.tree, 0, wx.EXPAND) 
        self.SetSizer(sizer) 

class MainFrame(wx.Frame): 

    def __init__(self): 
        wx.Frame.__init__(self, parent = None, title ='TreeCtrl Demo') 
        panel = TreePanel(self) 
        self.Show() 

if __name__ == '__main__': 
    app = wx.App(redirect = False) 
    frame = MainFrame() 
    app.MainLoop()
```

**输出:**

![](img/ec518586c744cce93bb476e26f416905.png)