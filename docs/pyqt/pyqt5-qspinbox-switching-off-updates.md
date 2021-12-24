# PyQt5 QSpinBox–关闭更新

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-关闭-更新/](https://www.geeksforgeeks.org/pyqt5-qspinbox-switching-off-updates/)

在本文中，我们将看到如何关闭旋转框的更新，关闭更新意味着它不会获得任何更新，如值的变化，甚至不会显示为`show`方法也不会对其产生影响。默认情况下，旋转框的更新处于打开状态。

为了做到这一点，我们使用`setUpdatesEnabled`方法。

> **语法:**旋转框. setUpdatesEnabled(False)
> 
> **自变量:**它以布尔为自变量
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

        # making spin box updates off
        self.spin.setUpdatesEnabled(False)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/798b17bd29dfcc7d03d94a3893599080.png)