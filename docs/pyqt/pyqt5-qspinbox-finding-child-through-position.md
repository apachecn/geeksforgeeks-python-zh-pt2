# PyQt5 QSpinBox–通过位置

查找孩子

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-find-child-through-position/](https://www.geeksforgeeks.org/pyqt5-qspinbox-finding-child-through-position/)

在本文中，我们将看到如何在旋转框内的给定位置获得旋转框的子元素，子元素基本上是旋转框的组成部分，例如，旋转框的主子元素是它的 QLineEdit，用于查看值和设置值。

为了做到这一点，我们使用`childAt`方法。

> **语法:**自旋 _box.childAt(x，y)
> 
> **自变量:**以位置为自变量，可以是 x，y 坐标或 QPoint 对象
> 
> **返回:**返回给定位置的子项，如果没有子项，则返回无

**注意:**坐标不属于窗口坐标系，它们在旋转框坐标系中

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

        # setting prefix to spin
        self.spin.setPrefix("Prefix ")

        # setting suffix to spin
        self.spin.setSuffix(" Suffix")

        # creating a label
        self.label = QLabel("Label ", self)

        # setting geometry to the label
        self.label.setGeometry(100, 200, 200, 70)

        # getting the child at the point 10, 10
        child = self.spin.childAt(10, 10)

        # setting text to the label
        self.label.setText(str(child))

        # making label multi line
        self.label.setWordWrap(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/1aee2f0bf9f434023f6aec58937113c0.png)