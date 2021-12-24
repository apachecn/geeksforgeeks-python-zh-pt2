# wx python–wx 中的 getclassdefaultattributes()。RadioButton

> 哎哎哎:# t0]https://www . geeksforgeeks . org/wx python-getclasdefaultattributes-in-wx radio/

Python 提供了 [**wxpython 包**](https://www.geeksforgeeks.org/python-wxpython-module-introduction/) ，让我们可以创建一个功能强大的图形用户界面。它被实现为一组扩展模块，包装了用 C++编写的 wxWidgets 库的 GUI 组件。它是一个跨平台的 python GUI 工具包，凤凰版凤凰是改进的下一代 wxPython，它主要关注速度、可维护性和可扩展性。

在本文中，我们将了解与 ***wx 相关联的***getclass defaultattributes()***函数。wxPython 的*** 类单选按钮。***GetClassDefaultAttributes()***功能用于返回 ***wx。可视化属性对象*** 用于属性，如背景色、前景色和与单选按钮相关的字体。

> **语法:** wx。radio button . GetClassDefaultAttributes(VARIANT = WINDOW _ VARIANT _ NORMAL)
> 
> **参数:**
> 
> <figure class="table">
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 不同的 | WindowVariant | 单选按钮的变体。 |
> 
> </figure>
> 
> **返回类型:** wx。视觉属性

**代码:**

## 蟒蛇 3

```py
# importing wx library
import wx

APP_EXIT = 1

# create an Example class
class Example(wx.Frame):
    # constructor
    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)

        # method calling
        self.InitUI()

    # method for user interface creation
    def InitUI(self):

        # create parent panel for radio buttons
        self.pnl = wx.Panel(self)

        # create radio button 
        self.rb = wx.RadioButton()
        self.rb.Create(self.pnl, id = 1 ,
                       label = "Radio",
                       pos = (20,20))

        # set background colour to blue
        self.rb.SetBackgroundColour((0, 0, 
                                     255, 255))
        # set foreground colour to white
        self.rb.SetForegroundColour((255, 255,
                                     255, 255))

        # create wx.VisualAttributes object
        v = self.rb.GetClassDefaultAttributes()

        # print background colour
        print(v.colBg)
        # print foreground colour
        print(v.colFg)

# main function
def main():
  # create an App object
  app = wx.App()

  # create an Example object
  ex = Example(None)
  ex.Show()

  # running an app
  app.MainLoop()

# Driver code
if __name__ == '__main__':

  # main function call
  main()
```

**输出:**

```py
(0,0,255,255, 255)
(255, 255, 255, 255)

```