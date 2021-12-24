# PyQt5 QSpinBox–如何设置蒙版

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-如何设置掩码/](https://www.geeksforgeeks.org/pyqt5-qspinbox-how-to-set-mask/)

在这篇文章中我们将看到如何设置遮罩到旋转框，遮罩基本上都是用来隐藏旋转框的，借助遮罩用户将无法看到整个旋转框虽然旋转框仍然会存在但上面会有遮罩。

为了做到这一点，我们使用了 setMask 方法。

> **语法:**旋转框.设置遮罩(区域)
> 
> **参数:**它以 QRegion 对象或 QBitMap 对象为参数
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
        self.spin.setRange(0, 999999)

        # setting prefix to spin
        self.spin.setPrefix("Prefix ")

        # setting suffix to spin
        self.spin.setSuffix(" Suffix")

        # getting the region of children of spin box
        region = self.spin.childrenRegion()

        # setting mask
        self.spin.setMask(region)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()
window.spin.setFocus()
# start the app
sys.exit(App.exec())
```

**输出:**
![](img/0daaded1cb7c900009243bd59243804b.png)