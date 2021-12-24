# PyQt5 QSpinBox–转储对象信息

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-dumping-object-information/](https://www.geeksforgeeks.org/pyqt5-qspinbox-dumping-object-information/)

在本文中，我们将看到如何转储旋转盒的对象信息，转储对象信息意味着转储关于信号连接的信息等。用于调试输出的旋转框。

> 为此，我们使用了 dumpObjectInfo 方法
> 
> **语法:**自旋 _box.dumpObjectInfo()
> 
> **论证:**不需要论证
> 
> **返回:**返回无

**注:**在 Qt 5.9 之前，该函数不是常值函数。

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

        # dumping object information of spin box
        self.spin.dumpObjectInfo()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()
window.spin.setFocus()
# start the app
sys.exit(App.exec())
```

**输出:**
![](img/c5b89fcb08616d965072840628f363a5.png)