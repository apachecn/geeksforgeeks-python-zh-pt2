# PyQt5 QSpinBox–获取字体的最小左方位

> 原文:[https://www . geesforgeks . org/pyqt5-qspinbox-获取字体的最小左方位/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-the-minimum-left-bearing-of-the-font/)

在本文中，我们将了解如何获得旋转框字体的最小左方位。最小左方位值是字体中所有字符的最小左方位值。左方位是字符最左边像素从字符逻辑原点向右的距离。如果字符的像素延伸到逻辑原点的左侧，则该值为负。

为了做到这一点，我们对旋转框的 QFontMetrics 对象使用`minLeftBearing()`方法。

> **语法:** font_metrics.minLeftBearing()
> 
> **论证:**不需要论证
> 
> **返回:**返回整数。

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
        self.spin.setRange(1, 999999)

        # setting prefix to spin
        self.spin.setPrefix("PREFIX ")

        # setting suffix to spin
        self.spin.setSuffix(" SUFFIX")

        # setting under line to the font
        font = self.spin.font()
        font.setUnderline(True)
        self.spin.setFont(font)

        # creating a label
        label = QLabel(self)

        # making label multi line
        label.setWordWrap(True)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 60)

        # getting font metrics
        f_metrics = self.spin.fontMetrics()

        # getting minimum left bearing value
        value = f_metrics.minLeftBearing()

        # setting text to the label
        label.setText("Min left bearing value : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/e63a86eeb2c78b5b5587781b1abad391.png)