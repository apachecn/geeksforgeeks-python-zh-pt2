# PyQt5–复选框

的检查状态()方法

> 原文:[https://www . geeksforgeeks . org/pyqt 5-check state-method-for-check-box/](https://www.geeksforgeeks.org/pyqt5-checkstate-method-for-check-box/)

复选框中基本上有两个状态是*选中*或*未选中*，虽然使用`setTristate`方法我们可以添加一个中间状态。

`checkState`方法用于检查复选框的状态，它返回 CheckState 对象但是当我们打印它时输出会如下:

*   0 表示未检查状态
*   2 表示选中状态
*   1 表示中间状态

> **语法:**复选框。检查状态()
> 
> **论证:**不需要论证。
> 
> **返回:**返回检查状态对象

下面是实现。

```
# importing libraries
from PyQt5.QtWidgets import * 
from PyQt5 import QtCore, QtGui
from PyQt5.QtGui import * 
from PyQt5.QtCore import * 
import sys

class Window(QMainWindow):

    def __init__(self):
        super().__init__()

        # setting title
        self.setWindowTitle("Python ")

        # setting geometry
        self.setGeometry(100, 100, 600, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for widgets
    def UiComponents(self):

        # creating the check-box
        checkbox = QCheckBox('Geek ?', self)

        # setting geometry of check box
        checkbox.setGeometry(200, 150, 100, 40)

        # getting the checked state
        check = checkbox.checkState()

        # printing the state
        print("Before check status : ", check)

        # checking the check box
        checkbox.setChecked(True)

        # getting the checked state
        check = checkbox.checkState()

        # printing the state
        print("After check status : ", check)

        # exiting the program
        sys.exit()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

```
Before check status :  0
After check status :  2
```