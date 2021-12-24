# PyQt5 QCalendarWidget–设置当前页面

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-setting-current-page/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-current-page/)

在本文中，我们将看到如何更改/设置 QCalendarWidget 的当前页面。QCalendarWidget 中的页面是给定年份的选定月份，更改页面也会更改月份和年份。

> 为此，我们将对 QCalendarWidget 对象使用 setCurrentPage 方法。
> **语法:** calendar.setCurrentPage(年、月)
> **自变量:**取两个整数作为自变量，即年、月
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

    # method for components
    def UiComponents(self):

        # creating a QCalendarWidget object
        calendar = QCalendarWidget(self)

        # setting geometry to the calendar
        calendar.setGeometry(10, 10, 400, 250)

        # year and month
        year = 1999
        month = 10

        # setting current page
        calendar.setCurrentPage(year, month)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/903e041e9bf2675f0cd1edd51e6b13eb.png)