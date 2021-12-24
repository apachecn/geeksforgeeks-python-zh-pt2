# PyQt5 QSpinBox–添加描述

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-add-description/](https://www.geeksforgeeks.org/pyqt5-qspinbox-adding-description/)

在本文中，我们将看到如何为旋转框设置描述，描述是关于组合框的详细信息，它讲述了功能用例和其他主要信息，以了解旋转框的工作。程序员使用描述来更好地理解程序。

为此，我们使用 **setAccessibleDescription** 方法。

> **语法:**旋转框. setAccessibleDescription(文本)
> 
> **自变量:**以字符串为自变量
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

        # setting prefix to spin
        self.spin.setPrefix("Prefix ")

        # setting suffix to spin
        self.spin.setSuffix(" Suffix")

        # text for description
        text = " This is description of spin box "

        # adding description ot the spin box
        self.spin.setAccessibleDescription(text)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/738455217d1ac139aa8e2f779b9428ee.png)