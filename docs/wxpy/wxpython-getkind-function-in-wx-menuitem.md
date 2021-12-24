# wx 中的 wxPython–GetKind()函数。菜单项

> 原文:[https://www . geesforgeks . org/wxpython-getkind-function-in-wx-menuitem/](https://www.geeksforgeeks.org/wxpython-getkind-function-in-wx-menuitem/)

在本文中，我们将学习与 wx 相关联的 GetKind()函数。wxPython 的 MenuItem 类。函数的作用是:返回项目类型，项目分隔符、项目正常、项目检查或项目单选中的一个。
不需要参数。

> **语法:**
> 
> ```
> wx.GetKind(self)
> 
> ```
> 
> **参数:**
> 
> ```
> No parameters are required in GetKind() function.
> 
> ```
> 
> **返回类型:**
> 
> ```
> wx.ItemKind
> 
> ```

**代码示例 1:**

```
import wx

class Example(wx.Frame):

    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)

        self.InitUI()

    def InitUI(self):
        self.locale = wx.Locale(wx.LANGUAGE_ENGLISH)

        self.menubar = wx.MenuBar()
        self.fileMenu = wx.Menu()
        self.item = wx.MenuItem(self.fileMenu, 1, '&Check', helpString ="Check Help", kind = wx.ITEM_RADIO)
        self.item.SetBitmap(wx.Bitmap('right.png'))
        self.fileMenu.Append(self.item)
        self.menubar.Append(self.fileMenu, '&File')
        self.SetMenuBar(self.menubar)
        # kind of menu item
        kind = self.item.GetKind()
        # print kind of menuitem
        print(kind)
        self.SetSize((350, 250))
        self.SetTitle('Icons and shortcuts')
        self.Centre()

def main():
    app = wx.App()
    ex = Example(None)
    ex.Show()
    app.MainLoop()

if __name__ == '__main__':
    main()
```

**输出:**

```
2 //2 corresponds to wx.ITEM_RADIO

```

**代码示例 2:**

```
import wx

class Example(wx.Frame):

    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)

        self.InitUI()

    def InitUI(self):
        self.locale = wx.Locale(wx.LANGUAGE_ENGLISH)

        self.menubar = wx.MenuBar()
        self.fileMenu = wx.Menu()
        self.item = wx.MenuItem(self.fileMenu, 1, '&Check', helpString ="Check Help")
        self.item.SetBitmap(wx.Bitmap('right.png'))
        self.fileMenu.Append(self.item)
        self.menubar.Append(self.fileMenu, '&File')
        self.SetMenuBar(self.menubar)
        # kind of menu item
        kind = self.item.GetKind()
        # print kind of menuitem
        print(kind)
        self.SetSize((350, 250))
        self.SetTitle('Icons and shortcuts')
        self.Centre()

def main():
    app = wx.App()
    ex = Example(None)
    ex.Show()
    app.MainLoop()

if __name__ == '__main__':
    main()
```

```
0 //0 corresponds to wx.ITEM_RADIO

```