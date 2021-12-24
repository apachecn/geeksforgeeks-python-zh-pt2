# PyQt5 QSpinBox–获取位置

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-get-position/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-position/)

在本文中，我们将了解如何获得旋转框的位置。位置是旋转框坐标所在的点。默认情况下，旋转框坐标为 0，0，尽管我们可以通过`setGeometry`方法或使用`move`方法来更改这一点。

为了做到这一点，我们对旋转框对象使用`pos`方法。

> **语法:**自旋 _box.pos()
> 
> **论证:**不需要论证
> 
> **返回:**返回 QPoint 对象

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

        # getting position
        value = self.spin.pos()

        # setting text to the label
        label.setText("Position : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/123a02fa85cc2260adff239c1cd2a56b.png)