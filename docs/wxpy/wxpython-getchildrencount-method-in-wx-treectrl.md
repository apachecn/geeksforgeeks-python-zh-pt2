# wx 中的 wxPython–getchildren count()方法。TreeCtrl

> 原文:[https://www . geesforgeks . org/wxpython-getchildren count-method-in-wx-tree ctrl/](https://www.geeksforgeeks.org/wxpython-getchildrencount-method-in-wx-treectrl/)

在本文中，我们将学习与 wx 相关联的 GetChildren 方法。wxPython 的 TreeCtrl 类。返回分支中的项数。GetChildren()方法接受两个参数第一个是 item，另一个是递归的。

递归是一个布尔参数，如果递归为 True，则返回后代的总数，否则只计算一级子代。GetChildrenCount()返回 int(与 TreeCtrl 项相关联的子级总数)。

> **语法:** wx。TreeCtrl.GetChildrenCount()

**参数:**

<figure class="table">

| **参数** | **类型** | **描述** |
| 项目 | wx(地名)。TreeItemId(树项目 Id) | 我们希望确保可见的项目。 |
| 递归地 | 布尔 | 递归或不递归地获取子对象。 |

</figure>

**例 1:**

## 计算机编程语言

```
import wx 

class MyTree(wx.TreeCtrl): 

    def __init__(self, parent, id, pos, size, style): 
        wx.TreeCtrl.__init__(self, parent, id, pos, size, style) 

class TreePanel(wx.Panel): 

    def __init__(self, parent): 
        wx.Panel.__init__(self, parent)

        # create tree control in window 
        self.tree = MyTree(self, wx.ID_ANY, wx.DefaultPosition, wx.DefaultSize, 
                        wx.TR_HAS_BUTTONS) 

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
        print(self.tree.GetChildrenCount(self.root, False))

        # expand all nodes of the tree
        self.tree.Expand() 

        sizer = wx.BoxSizer(wx.VERTICAL) 
        sizer.Add(self.tree, 100, wx.EXPAND) 
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

> Two

![](img/dda3780d456c96c2e6ced86e70ebe41b.png)

**例 2:**

## 计算机编程语言

```
import wx 

class MyTree(wx.TreeCtrl): 

    def __init__(self, parent, id, pos, size, style): 
        wx.TreeCtrl.__init__(self, parent, id, pos, size, style) 

class TreePanel(wx.Panel): 

    def __init__(self, parent): 
        wx.Panel.__init__(self, parent) 

        # create tree control in window 
        self.tree = MyTree(self, wx.ID_ANY, wx.DefaultPosition, wx.DefaultSize, 
                        wx.TR_HAS_BUTTONS) 

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
        print(self.tree.GetChildrenCount(self.root, True))

        # expand all nodes of the tree
        self.tree.ExpandAllChildren(item) 

        sizer = wx.BoxSizer(wx.VERTICAL) 
        sizer.Add(self.tree, 100, wx.EXPAND) 
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

> six

![](img/dda3780d456c96c2e6ced86e70ebe41b.png)