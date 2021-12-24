# wxPython–使用 Create()功能创建单选按钮

> 原文:[https://www . geesforgeks . org/wxpython-create-单选按钮-使用-create-function/](https://www.geeksforgeeks.org/wxpython-create-radio-button-using-create-function/)

**Create()** 功能用于 [**wxPython**](https://www.geeksforgeeks.org/python-wxpython-module-introduction/) 单选按钮的两步构建。 ***Create()*** 函数以单选按钮的不同属性为自变量

> **语法:** wx。RadioButton.Create(parent，id=ID_ANY，label= "，pos=DefaultPosition，size=DefaultSize，style=0，validator=DefaultValidator，name=RadioButtonNameStr)
> 
> **参数:**
> 
> <figure class="table">
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 父母 | wx。窗户 | 父窗口。不应该是无。 |
> | 身份证明（identification） | wx.窗口标识 | 控件标识符。值-1 表示默认值。 |
> | 标签 | 线 | 标示文字。 |
> | 刷卡机 | wx。要点 | 窗口位置。 |
> | 大小 | wx。窗户 | 窗口大小。 |
> | 风格 | 长的 | 窗口样式。 |
> | 验证器 | wx。验证器 | 窗口验证器。 |
> | 名字 | 线 | 窗口名称。 |
> 
> </figure>

**示例:**

## 蟒蛇 3

```
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

        # create parent panel in frame for radio button
        self.pnl = wx.Panel(self)

        # initialize radio button
        self.rb = wx.RadioButton()

        # create radio button with two step creation
        self.rb.Create(self.pnl, id = 1,
                       label = "Radio",
                       pos = (20,20))

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

![Radio button in wxpython](img/a2f9a99db7cb58dec6c6beebcb625311.png)