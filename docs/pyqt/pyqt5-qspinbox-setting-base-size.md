# PyQt5 QSpinBox–设置基本尺寸

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-setting-base-size/](https://www.geeksforgeeks.org/pyqt5-qspinbox-setting-base-size/)

在本文中，我们将看到如何设置旋转框的基本尺寸，如果旋转框定义了`sizeIncrement`，基本尺寸用于计算合适的旋转框尺寸。默认情况下，对于新创建的旋转框，此属性包含宽度和高度为零的大小。

下面是当主窗口变大时获得新旋转框大小的公式。

```py
width = baseSize().width() + i * sizeIncrement().width()
height = baseSize().height() + j * sizeIncrement().height()

Here i, j are the size increment in the main window

```

为了设置基本尺寸，我们使用了设置基本尺寸的方法。

> **语法:**旋转 _box.setBaseSize(宽度，高度)
> 
> **自变量:**取两个整数自变量，即底和高
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

        # setting base size
        self.spin.setBaseSize(250, 40)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/f6ce85c6d682b2f8be7b4db7f8f00eca.png)