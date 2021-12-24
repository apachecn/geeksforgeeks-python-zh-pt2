# PyQt5 QSpinBox–获取像素比例比例

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-get-pixel-ratio-scale/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-pixel-ratio-scale/)

在本文中，我们将看到如何获得旋转框的像素比例。设备像素比率是旋转框的物理像素和逻辑像素之间的比率。像素比标度是一种本质上是定量的可变测量标度。比率量表允许任何研究者比较间隔或差异。

> 为了做到这一点，我们使用设备像素比率缩放方法
> 
> **语法:**spin _ box . devicepixellratefscale()
> 
> **论证:**不需要论证
> 
> **返回:**返回浮动

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

        # getting pixel ratio scale
        pixel_ratio_scale = self.spin.devicePixelRatioFScale()

        # creating label
        label = QLabel(self)

        # setting geometry to the label
        label.setGeometry(100, 200, 200, 70)

        # making it multi line label
        label.setWordWrap(True)

        # setting text to the label
        label.setText("Pixel Ratio Scale : " + str(pixel_ratio_scale))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()
window.spin.setFocus()
# start the app
sys.exit(App.exec())
```

**输出:**
![](img/c9fbce770853d33af23bffdf87090f35.png)