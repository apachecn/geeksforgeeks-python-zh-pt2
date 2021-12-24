# wxPython–wx。wxPython 中的 DisplaySizeMM()函数

> 原文:[https://www . geeksforgeeks . org/wxpython-wx-displaysizemm-function-in-wxpython/](https://www.geeksforgeeks.org/wxpython-wx-displaysizemm-function-in-wxpython/)

在本文中，我们将了解 wxPython 中的 DisplaySizeMM()函数。DisplaySizeMM()函数是 wxPython 的父函数之一。DisplaySizeMM()函数与 DisplaySizeMM()函数相似，唯一的区别是 DisplaySizeMM()函数返回的尺寸单位是毫米。如果调用者对相应的值不感兴趣，则两个输出指针都可以是无。

> **语法:** wx。displaysizemm()
> 
> **参数:** DisplaySizeMM()函数不需要参数。
> 
> **返回:**(宽度、高度)
> 
> **返回类型:**元组

**Code Example:**

```py
# importing the module
import wx

# definition of the Example class
class Example(wx.Frame):

    # instantiating the class  
    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)

        self.InitUI()

    def InitUI(self):
        # print the size of display in millimeters
        print(wx.DisplaySizeMM())

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

```py
(406, 229)

```