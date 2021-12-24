# PyQt5–获取 QSpinBox 中的颜色计数

> 原文:[https://www . geeksforgeeks . org/pyqt 5-get-the-color-count-in-qspinbox/](https://www.geeksforgeeks.org/pyqt5-getting-the-color-count-in-qspinbox/)

在本文中，我们将看到如何获得旋转框的颜色计数，颜色计数基本上是旋转框可用的不同颜色的数量。有多种颜色的颜色计数，告诉可能的颜色数，可以设置到旋转框。

为此，我们使用**颜色计数**方法。

> **语法:**自旋 _box.colorCount()
> 
> **论证:**不需要论证
> 
> **返回:**返回整数，即旋转框的颜色计数值

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

        # creating label
        label = QLabel(self)

        # setting geometry to the label
        label.setGeometry(100, 200, 200, 70)

        # making it multi line label
        label.setWordWrap(True)

        # getting color count
        color_count = self.spin.colorCount()

        # setting to the label
        label.setText("Color Count : " + str(color_count))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()
window.spin.setFocus()
# start the app
sys.exit(App.exec())
```

**输出:**
![](img/a0c6b94bd31cf3768e245bd75677d258.png)