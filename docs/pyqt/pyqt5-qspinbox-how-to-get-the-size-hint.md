# PyQt5 QSpinBox–如何获取大小提示

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-如何获得大小提示/](https://www.geeksforgeeks.org/pyqt5-qspinbox-how-to-get-the-size-hint/)

在本文中，我们将看到如何获得旋转框的大小提示。大小提示是旋转框的建议大小。建议的大小与布局大小有关。如果窗口很大，小部件很少，那么大小提示会比正常情况下大。

为了做到这一点，我们对旋转框对象使用`sizeHint`方法。

> **语法:**自旋 _box.sizeHint()
> 
> **论证:**不需要论证
> 
> **返回:**返回 QSize 对象

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
        self.spin.setRange(0, 9)

        # setting prefix to spin
        self.spin.setPrefix("PREFIX ")

        # setting suffix to spin
        self.spin.setSuffix(" SUFFIX")

        # creating a label
        self.label = QLabel(self)

        # making label multi line
        self.label.setWordWrap(True)

        # setting label geometry
        self.label.setGeometry(100, 200, 250, 60)

        # getting the size hint
        value = self.spin.sizeHint()

        # setting text to the label
        self.label.setText("Recommended Size : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/fd8ce78120f5c51b0693e393eecf6f49.png)