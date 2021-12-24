# PyQt5 QSpinBox–获取上边距

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-get-top-margin/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-top-margin/)

在本文中，我们将看到如何获得旋转框的顶部边距，默认情况下它被设置为零，尽管我们可以使用旋转框的边距对象使用`setTop`方法来更改这一点。
为了做到这一点，我们使用**保证金制度**方法。

> **语法:** margin.top()
> 这里的 margin 是旋转框的 QMargin 对象
> 
> **论证:**不需要论证
> 
> **返回:**返回整数

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

        # creating label
        label = QLabel(self)

        # setting geometry to the label
        label.setGeometry(100, 200, 200, 70)

        # making it multi line label
        label.setWordWrap(True)

        # setting content margins
        self.spin.setContentsMargins(1, 2, 2, 1)

        # getting content margins
        margin = self.spin.contentsMargins()

        # getting top margin value
        top = margin.top()

        # setting text to the label
        label.setText("Top Margin = " + str(top))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()
window.spin.setFocus()
# start the app
sys.exit(App.exec())
```

**输出:**
![](img/94aab5fef9adf14b36e911a394e37fbb.png)