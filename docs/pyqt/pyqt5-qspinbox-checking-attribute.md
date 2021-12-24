# PyQt5 QSpinBox–检查属性

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-checking-attribute/](https://www.geeksforgeeks.org/pyqt5-qspinbox-checking-attribute/)

在本文中，我们将看到如何检查旋转框是否有给定的属性，属性基本上是旋转框的品质，一些属性类似于旋转框标志。旋转框有许多可用的属性，如 WA_AcceptDrops、WA _ AlwaysShowToolTips 等。

为了做到这一点，我们对旋转框对象使用`testAttribute`方法。

> **语法:** spin_box.testAttribute((Qt。WA_Disabled)
> 
> **参数:**它以 QWidget 属性对象为参数
> 
> **返回:**返回 bool

下面是实现

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

        # setting attribute to the spin box
        self.spin.setAttribute(Qt.WA_Disabled)

        # creating a label
        self.label = QLabel(self)

        # making label multi line
        self.label.setWordWrap(True)

        # setting label geometry
        self.label.setGeometry(100, 200, 250, 60)

        # checking if spin box has the disabled attribute
        value = self.spin.testAttribute(Qt.WA_Disabled)

        # setting text to the label
        self.label.setText("It has disabled attribute: " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/7e71d83ce35f1b7531c4141fb6555c01.png)