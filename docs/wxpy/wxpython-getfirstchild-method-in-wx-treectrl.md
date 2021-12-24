# wx 中的 wxPython–getfirst child()方法。TreeCtrl

> 原文:[https://www . geesforgeks . org/wxpython-getfirst child-method-in-wx-tree ctrl/](https://www.geeksforgeeks.org/wxpython-getfirstchild-method-in-wx-treectrl/)

**先决条件** : [wxPython](https://www.geeksforgeeks.org/python-wxpython-module-introduction/)

在本文中，我们将学习 wx 中的 GetFirstChild()方法。wxPython 的 TreeCtrl 类。GetFirstChild()方法返回第一个子级；为下一个孩子调用 GetNextChild。

这个函数需要一个“cookie”参数传递给它，这个参数对于应用程序来说是不透明的，但是对于库来说是必要的，以便让这些函数同时在同一个对象上枚举。传递给 GetFirstChild 和 GetNextChild 的 cookie 应该是同一个变量。

GetFirstChild()方法返回一个无效的树项(即 wx。如果没有其他子级，则返回 False。

> **语法:**
> 
> wx(地名)。TreeCtrl.GetFirstChild(self，item)
> 
> **参数:**
> 
> <figure class="table">
> 
> | **参数** | **类型** | **描述** |
> | 项目 | wx(地名)。TreeItemId(树项目 Id) | 我们希望确保可见的项目。 |
> 
> </figure>

**示例:**

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
        self.tree = MyTree(self, wx.ID_ANY, wx.DefaultPosition, wx.DefaultSize,
                           wx.TR_HAS_BUTTONS)
        # CREATE TREE ROOT
        self.root = self.tree.AddRoot('root')
        self.tree.SetPyData(self.root, ('key', 'value'))

        # add item to root
        item = self.tree.AppendItem(self.root, "Item")
        item2 = self.tree.AppendItem(self.root, "Item")

        L = self.tree.GetFirstChild(self.root)

        # print tuple of PySwigObject returned from GetFirstChild function
        print(L)

        # expand all nodes of the tree
        self.tree.ExpandAllChildren(item)

        sizer = wx.BoxSizer(wx.VERTICAL)
        sizer.Add(self.tree, 100, wx.EXPAND)
        self.SetSizer(sizer)

class MainFrame(wx.Frame):

    def __init__(self):
        wx.Frame.__init__(self, parent=None, title='TreeCtrl Demo')
        panel = TreePanel(self)
        self.Show()

if __name__ == '__main__':
    app = wx.App(redirect=False)
    frame = MainFrame()
    app.MainLoop()
```

**输出:**

> (<wx._controls.treeitemid proxy="" of="" object="" type="" at="">>、<swig object="" of="" type="" at="">)</swig></wx._controls.treeitemid>

![](img/90d6c31923346e2f0511e7e1cbf5c1c6.png)