# PyQt5 QSpinBox–设置背景角色

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-设置-背景-角色/](https://www.geeksforgeeks.org/pyqt5-qspinbox-setting-background-role/)

在本文中，我们将看到如何将背景角色设置为旋转框，旋转框中基本上有两种类型的角色，一种是前景，另一种是背景。背景角色从旋转框的调色板中定义用于渲染背景的画笔。如果未设置显式背景角色，旋转框将继承其父小部件的背景角色。

为此，我们使用了 setBackgroundRole 方法

> **语法:**spin _ box . setbackgroundrole(color _ object)
> T3】参数:需要 QPalette。ColorRole 对象参数
> **返回:**不返回

下面是实现

## 蟒蛇 3

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

        # setting prefix to spin
        self.spin.setPrefix("Prefix ")

        # setting suffix to spin
        self.spin.setSuffix(" Suffix")

        # making auto fill background of spin box
        self.spin.setAutoFillBackground(True)

        # setting background role
        self.spin.setBackgroundRole(QPalette.Base)

        # getting palette and setting color to the background to it
        p = self.spin.palette()
        p.setColor(self.spin.backgroundRole(), Qt.darkGray)
        self.spin.setPalette(p)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/c79acf848e2e819b4cee5e573c52f262.png)