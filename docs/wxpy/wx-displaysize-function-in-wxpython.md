# wx。wxPython 中的 DisplaySize()函数

> 原文:[https://www . geesforgeks . org/wx-display size-function-in-wxpython/](https://www.geeksforgeeks.org/wx-displaysize-function-in-wxpython/)

在本文中，我们将学习 wxPython 中的 DisplaySize()函数。DisplaySize()函数是 wxPython 的父函数之一。它以像素为单位返回显示大小。如果调用者对相应的值不感兴趣，则两个输出指针都可以是无。

> **语法:**
> wx。显示大小()
> 
> **参数:**
> DisplaySize()函数不需要参数。
> 
> **返回:**
> (宽、高)
> 
> **返回类型:**
> 元组

**代码示例:**

```
# importing the module
import wx

# definition of the Example class
class Example(wx.Frame):

    # instantiating the class
    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)

        self.InitUI()

    # method for creation of user interface
    def InitUI(self):

        # print the size of display
        print(wx.DisplaySize())

# definition of the main function
def main():

    # creating an App object
    app = wx.App()

    # creating an Example object
    ex = Example(None)

    # showing the Example object
    ex.Show()

    # running the App object
    app.MainLoop()

# driver code
if __name__ == '__main__':
    main()
```

**输出:**

```
(1536, 864)

```