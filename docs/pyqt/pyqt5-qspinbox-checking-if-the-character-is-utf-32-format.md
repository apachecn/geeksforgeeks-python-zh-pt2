# PyQt5 QSpinBox–检查字符是否为 UTF-32 格式

> 原文:[https://www . geesforgeks . org/pyqt5-qspinbox-checking-如果字符是 utf-32-format/](https://www.geeksforgeeks.org/pyqt5-qspinbox-checking-if-the-character-is-utf-32-format/)

在本文中，我们将看到如何检查旋转框字体中的给定字符是否为 UTF-32 格式。UTF-32 是一种用于编码 Unicode 码点的固定长度编码，每个码点正好使用 32 位。UTF-32 是一种固定长度编码，与所有其他 Unicode 转换格式不同，后者是可变长度编码。

为了做到这一点，我们对旋转框的 QFontMetrics 对象使用`inFontUcs4`方法。

> **语法:**font _ metrics . infontuc4(unit _ character)
> 
> **自变量:**以整数为自变量
> 
> **返回:**返回 bool。

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
        self.spin.setPrefix("PREFIX ")

        # setting suffix to spin
        self.spin.setSuffix(" SUFFIX")

        # creating a label
        label = QLabel(self)

        # making label multi line
        label.setWordWrap(True)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 60)

        # getting font metrics
        f_metrics = self.spin.fontMetrics()

        # checking if the character is in the font
        check = f_metrics.inFontUcs4(1)

        # setting text to the label
        label.setText(" UTF Format  : " + str(check))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/653a7910ff3b43bc5016e7abe873e359.png)