# wx。wxPython

中的 ColourDisplay()功能

> 原文:[https://www . geesforgeks . org/wx-color display-function-in-wxpython/](https://www.geeksforgeeks.org/wx-colourdisplay-function-in-wxpython/)

在本文中，我们将学习 wxPython 中的 ColourDisplay()方法。ColourDisplay()函数是 wxPython 中存在的一个内置函数。code > ColourDisplay()函数只是用来判断我们使用的显示器是否为彩色显示。如果显示是彩色的，函数返回真，否则返回假。

> **语法:**
> wx。color display()
> **参数:**
> color display()函数不需要参数。
> **返回类型:**
> bool

**代码示例:**

## 蟒蛇 3

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

        # condition for colour display
        if(wx.ColourDisplay()==True):

            # print if display is Colour display
            print("Display is Colour Display")

        else:

            # print if display is not Colour display
            print("Display is not Colour Display")

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
Display is Colour Display
```