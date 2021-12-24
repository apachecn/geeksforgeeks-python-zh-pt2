# wx python–getitemhelptext()wx 中的函数。收音机盒〔t1〕

> 哎哎哎:# t0]https://www . geeksforgeeks . org/wx python-getitemhelptext-function-in-wx-radio box/

在本文中，我们将学习与 wx 相关联的 GetItemHelpText()函数。wxPython 的 RadioBox 类。GetItemHelpText()函数只是用来返回与指定项(如果有)或“”关联的 HelpText。

它以项目索引为参数。

> **语法:**wx . radio box . getitemhelptext(self，item)
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 项目 | （同 Internationalorganizations）国际组织 | 从零开始的项索引。 |
> 
> **返回类型:**字符串

**代码示例:**

```
import wx

class FrameUI(wx.Frame):

    def __init__(self, parent, title):
        super(FrameUI, self).__init__(parent, title = title, size =(300, 200))

        # function for in-frame components
        self.InitUI()

    def InitUI(self):
        # parent panel for radio box
        pnl = wx.Panel(self)

        # list of choices
        lblList = ['Radio One', 'Radio Two']

        # create radio boc containing above list
        self.rbox = wx.RadioBox(pnl, label ='RadioBox', pos =(80, 10), choices = lblList,
                                         majorDimension = 1, style = wx.RA_SPECIFY_COLS)

        # set help for item index 1
        self.rbox.SetItemHelpText(1, "Second Item")

        # print help text associated with item index 1
        print (self.rbox.GetItemHelpText(1))

        # set frame in centre
        self.Centre()
        # set size of frame
        self.SetSize((400, 250))
        # show output frame
        self.Show(True)

# wx App instance
ex = wx.App()
# Example instance
FrameUI(None, 'RadioButton and RadioBox')
ex.MainLoop()
```

**控制台输出:**

```
Second Item

```

**输出窗口:**
![](img/f32eda796063b23b1250852322db8835.png)