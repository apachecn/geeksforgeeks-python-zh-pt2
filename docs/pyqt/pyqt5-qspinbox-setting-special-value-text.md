# PyQt5 QSpinBox–设置特殊值文本

> 原文:[https://www . geesforgeks . org/pyqt5-qspinbox-setting-special-value-text/](https://www.geeksforgeeks.org/pyqt5-qspinbox-setting-special-value-text/)

在本文中，我们将了解如何将特殊值文本设置到数字显示框中。每当当前值等于最小值时，将特殊值文本设置为数字显示框将显示该特殊文本而不是数值。这种情况的典型用法是表示这种选择具有特殊(默认)的含义。

为了做到这一点，我们对旋转框对象使用`setSpecialValueText`方法。

> **语法:**旋转框
> 
> **自变量:**以字符串为自变量
> 
> **返回:**返回无

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
        self.spin.setRange(0, 999999)

        # setting prefix to spin
        self.spin.setPrefix("PREFIX ")

        # setting suffix to spin
        self.spin.setSuffix(" SUFFIX")

        # setting special value text
        self.spin.setSpecialValueText("Geeks for Geeks")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-418718-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200527023620/Python-2020-05-27-02-35-54.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200527023620/Python-2020-05-27-02-35-54.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200527023620/Python-2020-05-27-02-35-54.mp4)</video>