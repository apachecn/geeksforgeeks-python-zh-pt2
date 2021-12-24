# PyQt5 QSpinBox–如何获取字体度量

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-如何获取字体度量/](https://www.geeksforgeeks.org/pyqt5-qspinbox-how-to-get-the-font-metrics/)

在本文中，我们将了解如何获得旋转框的字体度量。QFontMetrics 类提供字体度量信息，它计算给定字体的字符和字符串的大小。它基本上由旋转框字体的定位细节组成。

为了做到这一点，我们对旋转框对象使用`fontMetrics`方法。

> **语法:**自旋 _box.fontMetrics()
> 
> **论证:**不需要论证
> 
> **返回:**返回 QFontMetrics 对象

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

        # setting text to the label
        label.setText(str(f_metrics))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/301d54b00265824b6fe28031e70a9716.png)