# PyQt5 QSpinBox–检查子区域是否为空

> 原文:[https://www . geesforgeks . org/pyqt5-qspinbox-checking-children-region-is-empty-or-not/](https://www.geeksforgeeks.org/pyqt5-qspinbox-checking-if-children-region-is-empty-or-not/)

在本文中，我们将看到如何检查旋转框的子区域是否为空，子区域保存旋转框的子区域所占据的组合区域。为了做到这一点，我们使用`childrenRegion`方法。如果我们删除旋转框的所有子元素，那么这个属性将返回一个空区域。

为了做到这一点，我们使用 **isEmpty** 方法。

> **语法:** children_region.isEmpty()
> 
> **论证:**不需要论证
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

        # checking if children region is empty
        check = children_region.isEmpty()

        # setting text to the label
        label.setText("Children Region is empty ? " + str(check))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()
window.spin.setFocus()
# start the app
sys.exit(App.exec())
```

**输出:**
![](img/993db7b6aa4ea502530a27bfe1aa63f0.png)