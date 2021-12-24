# PyQt5 QSpinBox–访问光标

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-访问光标/](https://www.geeksforgeeks.org/pyqt5-qspinbox-accessing-the-cursor/)

在本文中，我们将了解如何获得旋转框的光标，光标是一种指示器，用于在计算机监视器或其他显示设备上显示用户交互的当前位置，这些显示设备将响应来自文本输入或定点设备的输入。我们用`setCursor`方法给它设置新的光标。

> 为了做到这一点，我们使用游标方法
> 
> **语法:**旋转框光标()
> 
> **论证:**不需要论证
> 
> **返回:**返回 QCursor 对象

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
        self.spin.setPrefix("Prefix ")

        # setting suffix to spin
        self.spin.setSuffix(" Suffix")

        # creating a cursor
        cursor = Qt.WaitCursor

        # setting cursor to the spin box
        self.spin.setCursor(cursor)

        # creating label
        label = QLabel(self)

        # setting geometry to the label
        label.setGeometry(100, 200, 200, 70)

        # making it multi line label
        label.setWordWrap(True)

        # getting cursor
        get_cursor = self.spin.cursor()

        # setting text to the label
        label.setText("Cursor : " + str(get_cursor))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()
window.spin.setFocus()
# start the app
sys.exit(App.exec())
```

**输出:**
![](img/fc577372778079401314111d69a2948e.png)