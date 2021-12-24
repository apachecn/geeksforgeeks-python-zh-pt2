# PyQt5 QSpinBox–获取文本的行距值

> 原文:[https://www . geesforgeks . org/pyqt5-qspinbox-get-line-spacing-value-the-text/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-the-line-spacing-value-of-the-text/)

在本文中，我们将了解如何获取旋转框文本的行距值。行距是从一条基线到下一条基线的距离。行距值始终等于文本的前导值和高度之和。

为了做到这一点，我们对旋转框的 QFontMetrics 对象使用`lineSpacing`方法。

> **语法:**font _ metrics . line space()
> 
> **论证:**不需要论证
> 
> **返回:**返回整数。

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
        self.spin.setRange(1, 999999)

        # setting prefix to spin
        self.spin.setPrefix("PREFIX ")

        # setting suffix to spin
        self.spin.setSuffix(" SUFFIX")

        # creating a label
        label = QLabel(self)

        # making label multi line
        label.setWordWrap(True)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 60)

        # getting font metrics
        f_metrics = self.spin.fontMetrics()

        # getting line spacing value
        value = f_metrics.lineSpacing()

        # setting text to the label
        label.setText(" Line Spacing  : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/f404b050d6793a008ccb539df66e3993.png)