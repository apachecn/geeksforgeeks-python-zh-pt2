# PyQt5 QSpinBox–访问最大值

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-access-maximum-value/](https://www.geeksforgeeks.org/pyqt5-qspinbox-accessing-maximum-value/)

在本文中，我们将看到如何获得最大值，即旋转框的上限，默认情况下，当我们创建一个旋转框时，它的范围从 0 到 99，即它的最大值是 99，尽管我们可以更改这一点。

为了做到这一点，我们将使用`spin_box.maximum`方法

> **语法:**自旋 _ box . max()
> 
> **论证:**不需要论证
> 
> **返回:**返回整数，即上键

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
        self.spin.setGeometry(100, 100, 100, 40)

        # setting maximum value
        self.spin.setMaximum(5)

        # creating label show result
        self.label = QLabel(self)

        # setting geometry
        self.label.setGeometry(100, 200, 200, 40)

        # getting max value
        val = self.spin.maximum()

        # setting text to the label
        self.label.setText("Max Value  : " + str(val))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

window.show()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/8e172a16dd131131547cc516ba08f4f4.png)