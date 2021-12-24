# PyQt5 QSpinBox–获得有孩子的联合区域

> 原文:[https://www . geesforgeks . org/pyqt5-qspinbox-get-the-United-region-with-children-region/](https://www.geeksforgeeks.org/pyqt5-qspinbox-get-the-united-region-with-children-region/)

在本文中，我们将看到如何将旋转框的子区域和另一个区域联合起来，子区域保存旋转框的子区域所占据的组合区域。为了得到孩子区域，我们使用`childrenRegion`方法。联合区域将是儿童区域和儿童区域的联盟

> 为了做到这一点，我们对旋转框的子区域对象使用联合方法
> 
> **语法:** children_region.united(矩形)
> 
> **自变量:**它以 QRect 为自变量，也可以取 QRegion
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

        # QRect
        rectangle = QRect(200, 200, 40, 50)

        # getting united region with the children region
        children_region = children_region.united(rectangle)

        # setting text to the label
        label.setText("United region : " + str(children_region.rects()))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()
window.spin.setFocus()
# start the app
sys.exit(App.exec())
```

**输出:**
![](img/050915ca0d69af4e0b81e6be679bb88a.png)