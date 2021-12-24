# PyQt5 QSpinBox–为其设置标题

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-setting-caption-to-it/](https://www.geeksforgeeks.org/pyqt5-qspinbox-setting-caption-to-it/)

在本文中，我们将看到如何为旋转框设置标题，标题基本上是旋转框的标题，但它不可见标题仅用于后端目的。旋转框的标题类似于主窗口的标题。

为了做到这一点，我们使用`setWindowTitle`方法。

> **语法:** spin_box.setWindowTitle(标题)
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

        # caption
        caption = "Spin Box 01"

        # setting caption
        self.spin.setWindowTitle(caption)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/494aeffe9f477ffc86a0ac2e7540c553.png)