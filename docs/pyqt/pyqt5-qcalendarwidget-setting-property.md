# PyQt5 QCalendarWidget–设置属性

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-setting-property/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-property/)

在本文中，我们将看到如何为 QCalendarWidget 设置属性信息，属性是开发人员添加的信息，用于讲述日历的属性，例如，如果日历有一个阻止的未来日期，开发人员将添加该属性，以便其他开发人员可以看到该属性并了解该属性。

> 为此，我们将对 QCalendarWidget 对象使用 setProperty 方法。
> **语法:**calendar . set property(property，value)
> **参数:**它需要两个参数一个是字符串，另一个是整数
> **返回:**它不返回

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

        # setting cursor
        self.calendar.setCursor(Qt.PointingHandCursor)

        # setting properties
        self.calendar.setProperty("Blocked Dates ?: ", 0)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()
window.calendar.destroy()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/882493a687aa2c111c0389ccbccc3cca.png)