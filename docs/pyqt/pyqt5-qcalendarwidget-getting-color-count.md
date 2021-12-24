# PyQt5 QCalendarWidget–获取颜色计数

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-get-color-count/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-getting-color-count/)

在本文中，我们将看到如何获得 QCalendarWidget 的颜色计数。颜色计数基本上是日历可用的不同颜色的数量。有多种颜色颜色计数告诉可能的颜色数量，可以设置为日历。

> 为此，我们将对 QCalendarWidget 对象使用 colorCount 方法。
> **语法:**calendar . colorcount()
> **参数:**不需要参数
> **返回:**返回整数

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

        # setting focus
        self.calendar.setFocus(Qt.NoFocusReason)

        # creating a label
        label = QLabel(self)

        # setting geometry
        label.setGeometry(50, 280, 420, 120)

        # making it multi line
        label.setWordWrap(True)

        # getting color count
        value = self.calendar.colorCount()

        # setting text to the label
        label.setText("Color count : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/1844b754a64169c36dae546e47a924f0.png)