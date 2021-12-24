# PyQt5 QCalendarWidget–位深

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-bit-depth/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-bit-depth/)

在本文中，我们将看到如何获得 QCalendarWidget 的深度。颜色深度或颜色深度，也称为位深度，或者是在本日历中用于指示单个像素颜色的位数，或者是用于单个像素的每个颜色分量的位数。

> 为此，我们将对 QCalendarWidget 对象使用深度方法。
> **语法:** calendar.depth()
> **参数:**不需要参数
> **返回:**返回整数

下面是实现

## 蟒蛇 3

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
        self.setGeometry(100, 100, 650, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        # creating a QCalendarWidget object
        self.calendar = QCalendarWidget(self)

        # setting geometry to the calendar
        self.calendar.setGeometry(50, 10, 400, 250)

        # setting cursor
        self.calendar.setCursor(Qt.PointingHandCursor)

        # creating a label
        label = QLabel(self)

        # setting geometry
        label.setGeometry(50, 280, 420, 120)

        # making it multi line
        label.setWordWrap(True)

        # getting depth
        value = self.calendar.depth()

        # setting text to the label
        label.setText("Depth  " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/b4ec81cc219ac0292f9acd575939e31e.png)