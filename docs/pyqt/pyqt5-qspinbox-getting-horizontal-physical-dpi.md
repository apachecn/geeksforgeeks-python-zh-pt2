# PyQt5 QSpinBox–获取水平物理 DPI

> 原文:[https://www . geesforgeks . org/pyqt5-qspinbox-get-horizontal-physical-dpi/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-horizontal-physical-dpi/)

在本文中，我们将了解如何获得旋转框的水平物理 DPI。DPI 是指当图像被复制为真实的物理实体(例如打印到纸上)时的物理点密度。数字存储的图像没有以英寸或厘米为单位的固有物理尺寸。

为了做到这一点，我们对旋转框对象使用`physicalDpiX`方法。

> **语法:** spin_box.physicalDpiX()
> 
> **论证:**不需要论证
> 
> **返回:**返回整数

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

        # creating a label
        label = QLabel(self)

        # making the label multi line
        label.setWordWrap(True)

        # setting geometry to the label
        label.setGeometry(100, 200, 200, 60)

        # getting horizontal Physical DPI
        value = self.spin.physicalDpiX()

        # setting text to the label
        label.setText("Horizontal Physical DPI : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/65a2716e2d77db372e4baff8ee357955.png)