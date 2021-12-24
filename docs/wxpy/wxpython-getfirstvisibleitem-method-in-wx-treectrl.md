# wx python–getfirstvisiblement()方法在 wx 中。tree ctrl〔t1〕

> 哎哎哎:# t0]https://www . geeksforgeeks . org/wx python-getfirstvisibletem-method-in-wx-tree ctrl/

在本文中，我们将讨论与 wx 相关联的 GetFirstVisibleItem()函数。wxPython 的 TreeCtrl 类。让我们看看它是如何使用的，以及它的用途:

> **语法:** wx。treectrl . getfirstvisibleitemid(自我)
> 
> **参数:**
> 
> GetFirstVisibleItemId()方法不需要任何参数。
> 
> **返回:**
> 
> wx。TreeItemId 对象，它是树的第一个可见项

其实现如下:

如果第一个可见项目有效或无效，则打印以下示例。我们将使用与 wx 相关联的 IsOk()方法来执行这个操作。方法，如果树项是有效项，则返回 true。

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

        # print if first visible item is a valid tree item
        if(self.tree.GetFirstVisibleItem().IsOk()):
            print("Is Valid Item")
        else:
            print("Invalid Tree Item")

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

> 是有效项目

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

        # print if first visible item is a valid tree item
        if(self.tree.GetFirstVisibleItem().IsOk()):
            print("Is Valid Item")
        else:
            print("Invalid Tree Item")

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

> 无效的树项目