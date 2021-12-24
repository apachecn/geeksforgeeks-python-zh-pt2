# pyqt 5 qsp box–本地设置

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-setting-locale/](https://www.geeksforgeeks.org/pyqt5-qspinbox-setting-locale/)

在本文中，我们将了解如何将区域设置设置为旋转框。只要没有设置特殊的区域设置，微调框的区域设置要么是父控件的区域设置，要么如果给定的微调框是顶级小部件，那么它就有自己的默认区域设置。虽然我们也可以为旋转盒设置一个特殊的自定义。

为了做到这一点，我们对旋转框对象使用`setLocale`方法。

> **语法:** spin_box.setLocale(本端)
> 
> **自变量:**它以 QLocale 对象为自变量
> 
> **返回:**返回无

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

        # locale
        locale = QLocale()

        # setting locale to the spin box
        self.spin.setLocale(locale)

        # creating a label
        label = QLabel(self)

        # making the label multi line
        label.setWordWrap(True)

        # setting geometry to the label
        label.setGeometry(100, 200, 200, 60)

        # getting the locale of the spin box
        value = self.spin.locale()

        # setting text to the label
        label.setText("New Locale : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/69805024705fcaf4808b5ed1790c0aac.png)