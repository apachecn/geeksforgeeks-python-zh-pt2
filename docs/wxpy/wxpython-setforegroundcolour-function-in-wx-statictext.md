# wx Tyson–wx 中的 SetForegroundColour()函数。StaticText

> 原文:[https://www . geeksforgeeks . org/wxpython-setforegroundcolour-function-in-wx-static text/](https://www.geeksforgeeks.org/wxpython-setforegroundcolour-function-in-wx-statictext/)

在本文中，我们将学习与 wx 相关的 SetForegroundColour()函数。wxPython 的 StaticText 类。函数的作用是将静态文本的前景色设置成不同的颜色。

它需要 wx。设置背景颜色的颜色参数。

> **语法:** wx。设置背景颜色(自身，颜色)
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 颜色 | wx。颜色 | 要设置的前景色。 |

**代码示例:**

```
import wx

class Example(wx.Frame):

    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)
        self.InitUI()

    def InitUI(self):
        self.locale = wx.Locale(wx.LANGUAGE_ENGLISH)
        self.pnl = wx.Panel(self)

        bmp = wx.Bitmap('right.png')
        # CREATE STATICTEXT AT POINT (20, 20)
        self.st = wx.StaticText(self.pnl, id = 1, label ="This is the Label.", 
                                pos =(20, 20), size = wx.DefaultSize, 
                           style = wx.ST_ELLIPSIZE_MIDDLE, name ="statictext")

        # SET FOREGROUND COLOUR TO YELLOW
        self.st.SetForegroundColour((3, 152, 252, 255))
        self.SetSize((350, 250))
        self.SetTitle('wx.Button')
        self.Centre()

def main():
    app = wx.App()
    ex = Example(None)
    ex.Show()
    app.MainLoop()

if __name__ == '__main__':
    main()
```

**输出窗口:**
![](img/1f442ee1f11aa72a492778de0c31dd92.png)