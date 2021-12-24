# PyQt5 QSpinBox–如何保存其几何图形

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-如何保存其几何图形/](https://www.geeksforgeeks.org/pyqt5-qspinbox-how-to-save-its-geometry/)

在本文中，我们将看到如何保存旋转框的几何图形。保存几何有助于保存顶层旋转框小部件的当前几何和状态。保存的数据可以存储在任何外部文件中，也可以恢复为其他用途。

为了做到这一点，我们对旋转框对象使用`saveGeometry`方法。

> **语法:**旋转 _box.saveGeometry()
> 
> **论证:**不需要论证
> 
> **返回:**返回 QByteArray 对象

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

        # saving the geometry
        value = self.spin.saveGeometry()

        # setting text to the label
        label.setText("Saved geometry : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/71e8883894c2add65d27ed934d662b6b.png)