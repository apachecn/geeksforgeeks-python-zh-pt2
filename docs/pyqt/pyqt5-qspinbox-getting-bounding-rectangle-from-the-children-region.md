# PyQt5 QSpinBox–从子区域获取边框

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-从儿童区域获取边框/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-bounding-rectangle-from-the-children-region/)

在本文中，我们将看到如何从旋转框的子区域获得边框，子区域保存旋转框的子区域占据的组合区域。为了得到孩子区域，我们使用`childrenRegion`方法。边框是指覆盖整个子区域的矩形。

> 为此，我们对旋转框的子区域对象使用`boundingRect`方法
> 
> **语法:**children _ region . boundingrect()
> 
> **论证:**不需要论证
> 
> **返回:**返回 QRect 对象

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

        # setting geometry to the label
        label.setGeometry(100, 200, 200, 30)

        # getting bounding rectangle from the children region
        bounding_rectangle = children_region.boundingRect()

        # setting text to the label
        label.setText(str(bounding_rectangle))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()
window.spin.setFocus()
# start the app
sys.exit(App.exec())
```

**输出:**
![](img/cce18571d47041683e34792500198668.png)