# PyQt5 QSpinBox–如何获取左边距

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-如何获取左边距/](https://www.geeksforgeeks.org/pyqt5-qspinbox-how-to-get-left-margin/)

在这篇文章中，我们将看到如何获得旋转框的左边距，默认情况下它被设置为零，尽管我们可以使用旋转框的边距对象使用`setLeft`方法来改变这一点。

为此，我们使用**左边距**方法。

> **语法:** margin.left()
> 这里的 margin 是旋转框的 QMargin 对象
> 
> **论证:**不需要论证
> 
> **返回:**返回整数

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

        # getting content margins
        margin = self.spin.contentsMargins()

        # getting left margin value
        left = margin.left()

        # setting text to the label
        label.setText("Left Margin = " + str(left))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()
window.spin.setFocus()
# start the app
sys.exit(App.exec())
```

**输出:**
![](img/9cf32533cc0af72ecd21d758e1340f22.png)