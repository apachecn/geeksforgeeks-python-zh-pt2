# PyQt5 QSpinBox–检查某个点是否在子区域

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-检查某个点是否在儿童区域/](https://www.geeksforgeeks.org/pyqt5-qspinbox-checking-if-certain-point-is-in-the-children-region/)

在本文中，我们将看到如何检查旋转框的子区域中的某个点，子区域包含旋转框的子区域所占据的组合区域。为了做到这一点，我们使用`childrenRegion`方法。

**注意:**该点应在旋转框坐标系统中

> 为此，我们对旋转框的子区域对象使用 contains 方法
> 
> **语法:** children_region.contains(点)
> 
> **自变量:**它以 QPoint 对象为自变量
> 
> **返回:**返回布尔对象

下面是实现

```
# Write Python3 code here# importing libraries
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

        # getting bounding rectangle from the children region
        bounding_rectangle = children_region.contains(QPoint(10, 10))

        # setting text to the label
        label.setText("Point 10, 10 of spin box is in the children region "
                      "? " + str(bounding_rectangle))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()
window.spin.setFocus()
# start the app
sys.exit(App.exec())
```

**输出:**
![](img/68712f10a4b4d1faa35231193f22e9ac.png)