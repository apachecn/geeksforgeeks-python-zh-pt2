# PyQt5 QSpinBox–检查边距是否为空？

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-checking-if-margin-null/](https://www.geeksforgeeks.org/pyqt5-qspinbox-checking-if-margin-is-null/)

在本文中，我们将看到如何检查旋转框的边距是否为空，默认情况下，它被设置为零，尽管我们可以使用旋转框对象的`setContentsMargins`方法来更改这一点。如果任何边距值大于 0，则旋转框边距不为空。

**注意:**当每个边距值设置为 0 时，表示它们为空

为了做到这一点，我们使用**是完整的**方法。

> **语法:** margin.isNull()
> 这里的 margin 是旋转框的 QMargin 对象
> 
> **论证:**不需要论证
> 
> **返回:**返回 bool

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

        # creating label
        label = QLabel(self)

        # setting geometry to the label
        label.setGeometry(100, 200, 200, 70)

        # making it multi line label
        label.setWordWrap(True)

        # setting content margins
        self.spin.setContentsMargins(1, 0, 0, 0)

        # getting content margins
        margin = self.spin.contentsMargins()

        # checking if margin is NULL
        check = margin.isNull()

        # setting text to the label
        label.setText("BMargin is NULL ? : " + str(check))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()
window.spin.setFocus()
# start the app
sys.exit(App.exec())
```

**输出:**
![](img/9ed87073ad1828d4c9a0873ac46c50c0.png)