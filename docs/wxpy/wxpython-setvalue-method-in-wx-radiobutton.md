# wx 中的 wxPython–SetValue()方法。单选按钮

> 原文:[https://www . geesforgeks . org/wxpython-set value-method-in-wx-radio button/](https://www.geeksforgeeks.org/wxpython-setvalue-method-in-wx-radiobutton/)

Python 提供了[**【wxpython】**](https://www.geeksforgeeks.org/python-wxpython-module-introduction/)****包**，允许我们创建高功能的图形用户界面。它是一个跨平台的 Python GUI 工具包，凤凰版凤凰是改进的下一代 wxPython，它主要关注速度、可维护性和可扩展性。**

**在本文中，我们将学习与 **wx 相关联的***【SetValue()*****方法。wxPython 的 RadioButton** 类。 ***SetValue()*** 方法将单选按钮设置为选中或未选中状态。这不会导致发出 **wxEVT_RADIOBUTTON** 事件。如果单选按钮属于某个单选按钮组，则可以选中该组中的一个按钮，因此只能在值设置为“真”时调用此方法。要取消选中一个组中的单选按钮，您必须选中同一组中的另一个按钮。**** 

> ******语法:** wx。设置值(自身，值)****

******参数:******

<figure class="table">

| 参数 | 输入类型 | 描述 |
| --- | --- | --- |
| 价值 | 弯曲件 | 如果为真，则选中；如果为假，则取消选中。 |

</figure>

******示例:******

## ****蟒蛇 3****

```
**# importing wx library
import wx

APP_EXIT = 1

# create a Example class
class Example(wx.Frame):
    # constructor
    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)

        # method calling
        self.InitUI()

    # method for user interface creation
    def InitUI(self):

        # parent panel for radio buttons
        self.pnl = wx.Panel(self)

        # create radio buttons
        self.rb1 = wx.RadioButton(self.pnl,
                                  label = 'Button 1',
                                  pos = (30, 10))
        self.rb2 = wx.RadioButton(self.pnl,
                                  label = 'Button 2',
                                  pos = (30, 30))
        self.rb3 = wx.RadioButton(self.pnl,
                                  label = 'Button 3',
                                  pos = (30, 50))

        # set value for the second radio button as true(checked)
        self.rb2.SetValue(True)

# main function
def main():

  # create an App object
  app = wx.App()

  # create an Example object
  ex = Example(None)
  ex.Show()

  # running a app
  app.MainLoop()

# Driver code
if __name__ == '__main__':

  # main function call
  main()**
```

******输出:****** 

****![](img/afb12b24f8a30073dbde702cae67dafa.png)

单选按钮****