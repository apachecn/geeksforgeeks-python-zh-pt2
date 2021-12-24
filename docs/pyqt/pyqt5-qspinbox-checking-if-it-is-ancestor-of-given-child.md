# PyQt5 QSpinBox–检查它是否是给定子代的祖先

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-检查它是否是给定孩子的祖先/](https://www.geeksforgeeks.org/pyqt5-qspinbox-checking-if-it-is-ancestor-of-given-child/)

在本文中，我们将看到如何检查旋转框是否是给定子对象的祖先。如果旋转框是给定子对象的父对象(或祖父母，等等)，并且旋转框和子对象都在同一个窗口中，那么它就是祖先，否则就不是。

为了做到这一点，我们对旋转框对象使用`isAncestorOf`方法。

> **语法:**旋转框.拜斯托尔弗(子)
> 
> **参数:**取 QWidget 对象参数
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

        # getting child of spin box
        child = self.spin.children()[0]

        # creating a label
        label = QLabel(self)

        # making the label multi line
        label.setWordWrap(True)

        # setting geometry to the label
        label.setGeometry(100, 200, 200, 60)

        # checking if spin box is ancestor
        check = self.spin.isAncestorOf(child)

        # setting text to the label
        label.setText("Ancestor ?  : " + str(check))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/b10ff08aaf1e3806c8f4ea8c7baf9b43.png)