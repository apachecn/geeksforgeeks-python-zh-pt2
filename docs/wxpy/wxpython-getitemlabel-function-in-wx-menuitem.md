# wx python–wx 中的 GetItemLabel()函数。MenuItem

> 哎哎哎:# t0]https://www . geeksforgeeks . org/wx python-getitem label-function-in-wx-menu item/

在本文中，我们将学习与 wx 相关联的 GetItemLabel()函数。wxPython 的 MenuItem 类。函数的作用是:简单地返回与菜单项相关的文本，包括传递给构造函数或 SetItemLabel 的任何加速器字符。
GetItemLabel()函数不取参数。

> **语法:**
> 
> ```
> wx.MenuItem.GetItemLabel(self)
> ```
> 
> **参数:**
> 
> ```
> No Parameters are required in wx.MenuItem.
> ```
> 
> **返回类型:**
> 
> ```
> string
> ```

**代码示例:**

## 蟒蛇 3

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
        self.st = wx.StaticText(self, label ="", pos =(20, 20), style = wx.ALIGN_LEFT)
        self.fileMenu.Append(self.item)
        self.menubar.Append(self.fileMenu, '&File')
        self.SetMenuBar(self.menubar)
        # label associated with 'item' menuitem
        label = self.item.GetItemLabel()
        # print label
        print(label)
        self.st.SetLabel(label)
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
&Check
```

**输出窗口:**

![](img/498bfa8c0d1e2e048e8174843d06986d.png)