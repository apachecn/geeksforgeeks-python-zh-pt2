# PyQt5 QSpinBox–获得毫米高度

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-get-mm-height/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-mm-height/)

在本文中，我们将了解如何获得旋转框的毫米高度。毫米高度基本上是油漆设备的高度，单位为毫米。由于平台限制，可能无法使用此功能来确定屏幕上旋转框的实际物理大小。

为了做到这一点，我们对旋转框对象使用`heightMM`方法。

> **语法:**自旋 _box.heightMM()
> 
> **论证:**不需要论证
> 
> **返回:**返回整数

下面是实现

```py
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
        # creating spin box
        self.spin = QSpinBox(self)

        # setting geometry to spin box
        self.spin.setGeometry(100, 100, 250, 40)

        # setting range to the spin box
        self.spin.setRange(1, 999999)

        # setting prefix to spin
        self.spin.setPrefix("PREFIX ")

        # setting suffix to spin
        self.spin.setSuffix(" SUFFIX")

        # creating a label
        label = QLabel(self)

        # making the label multi line
        label.setWordWrap(True)

        # setting geometry to the label
        label.setGeometry(100, 200, 200, 60)

        # getting MM Height of spin box
        value = self.spin.heightMM()

        # setting text to the label
        label.setText("MM Height =  " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/3583b382bd92f3bd144e32e4f7efa40a.png)