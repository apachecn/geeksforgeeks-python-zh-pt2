# PyQt5–复选框

的 isTristate()方法

> 原文:[https://www . geesforgeks . org/pyqt 5-ististate-method-for-check-box/](https://www.geeksforgeeks.org/pyqt5-istristate-method-for-check-box/)

当我们在 PyQt5 应用程序中创建复选框时，默认情况下它只有两种状态，即真和假，但借助`setTristate`方法。`isTristate`方法用于检查复选框是否有两种状态或三种状态，如果复选框有三种状态，则返回真，否则返回假。

> **语法:**复选框。ististate()
> 
> **论证:**不需要论证。
> 
> **返回:**返回 bool，如果是三态则返回 True，否则返回 False。

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
        checkbox = QCheckBox('Check Box', self)

        # setting geometry of check box
        checkbox.setGeometry(200, 150, 100, 30)

        # creating the third state
        checkbox.setTristate(True)

        # getting if check bos is tri-state
        check = checkbox.isTristate()

        # printing the check
        print(check)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

```
True
```

![](img/5fb126502435b1250c5ee45f187e8da8.png)