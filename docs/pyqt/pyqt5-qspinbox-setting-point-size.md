# PyQt5 QSpinBox–设定点尺寸

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-setting-point-size/](https://www.geeksforgeeks.org/pyqt5-qspinbox-setting-point-size/)

在本文中，我们将看到如何在旋转框中设置文本的磅值。改变点的大小会改变文字的大小，像素和点是两回事有些东西点里面可以有多个像素。建议更改点大小以改变文本的大小。

为了做到这一点，我们对旋转框的 QFont 对象使用`setPointSize`方法

> **语法:** font.setPointSize(n)
> 
> **自变量:**以整数为自变量
> 
> **返回:**返回无

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

        # getting font of the spin box
        font = self.spin.font()

        # setting point size
        font.setPointSize(20)

        # reassigning this font to the spin box
        self.spin.setFont(font)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/424c9abc24e3c8dd4c5c165f1ef42853.png)