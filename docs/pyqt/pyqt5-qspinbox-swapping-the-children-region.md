# PyQt5 QSpinBox–交换子区域

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-交换-孩子-地区/](https://www.geeksforgeeks.org/pyqt5-qspinbox-swapping-the-children-region/)

在本文中，我们将看到如何将旋转框的子区域与另一个区域交换，子区域保存旋转框的子区域所占据的组合区域。为了得到孩子区域，我们使用`childrenRegion`方法。

> 为此，我们对旋转框的子区域对象使用交换方法
> 
> **语法:** children_region.swap(region)
> 
> **自变量:**它以 QRegion 对象为自变量
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
        self.spin.setPrefix("Prefix ")

        # setting suffix to spin
        self.spin.setSuffix(" Suffix")

        # getting the children region
        children_region = self.spin.childrenRegion()

        # creating a label
        label = QLabel(self)
        label.setWordWrap(True)

        # setting geometry to the label
        label.setGeometry(100, 200, 200, 60)

        # creating a region
        region = QRegion(QRect(300, 1, 20, 20))

        # subtracting a region
        children_region.swap(region)

        # setting text to the label
        label.setText("Swapped region : " + str(children_region))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()
window.spin.setFocus()
# start the app
sys.exit(App.exec())
```

**输出:**
![](img/6d2aabc93a9e3cdd9378399fb75eb2cf.png)