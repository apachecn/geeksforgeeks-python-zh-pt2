# PyQt5 QSpinBox–获取与子区域的异或区域

> 原文:[https://www . geesforgeks . org/pyqt5-qspinbox-get-the-xor-region-with-children-region/](https://www.geeksforgeeks.org/pyqt5-qspinbox-get-the-xor-region-with-children-region/)

在本文中，我们将看到如何得到异或，即与旋转框的子区域和另一个区域异或，子区域保存旋转框的子区域占据的组合区域。为了得到孩子区域，我们使用`childrenRegion`方法。异或区域将是没有交集部分的新区域。下面是异或区域的外观。

![](img/bffe4311842f5b1ddc9280e127bba314.png)

> 为此，我们对旋转框的子区域对象使用 xored 方法
> 
> **语法:** children_region.xored(区域)
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
        label.setGeometry(100, 200, 200, 80)

        # QRegion
        region = QRegion(QRect(40, 10, 40, 50))

        # getting XOR region
        children_region = children_region.xored(region)

        # setting text to the label
        label.setText("XOR Rectangles : " + str(children_region.rects()))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()
window.spin.setFocus()
# start the app
sys.exit(App.exec())
```

**输出:**
![](img/2b16d0c553b5a7e9b24692dedb16f4f9.png)