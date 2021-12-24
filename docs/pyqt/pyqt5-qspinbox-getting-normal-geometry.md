# PyQt5 QSpinBox–获取正常几何图形

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-get-normal-geometry/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-normal-geometry/)

在这篇文章中，我们将看到我们如何可以得到自旋盒的正常几何。旋转的正常几何是当显示为顶级小部件的正常(非最大化或全屏)时将出现的几何。对于子小部件，正常的几何图形总是包含一个空的矩形。默认情况下，普通几何图形包含一个空矩形。

为了做到这一点，我们对旋转框对象使用`normalGeometry`方法。

> **语法:**自旋 _box.normalGeometry()
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

        # getting normal geometry of the spin box
        value = self.spin.normalGeometry()

        # setting text to the label
        label.setText("Normal geometry : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/c1e1090fa5a3011bf8cd1addcc35e780.png)