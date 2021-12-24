# PyQt5 QCalendarWidget–获取当前年份

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-get-current-year/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-getting-current-year/)

在本文中，我们将看到如何获得 QCalendarWidget 的当前年份。当前年份是日历上显示的年份，即当前页面年份。我们可以借助 setCurrentPage 方法设置页面。

> 为此，我们将对 QCalendarWidget 对象使用 yearShown 方法。
> **语法:**calendar . yearhow()
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

        # creating a label
        label = QLabel(self)

        # setting geometry to the label
        label.setGeometry(100, 280, 250, 60)

        # making label multi line
        label.setWordWrap(True)

        # getting current year
        value = calendar.yearShown()

        # setting text to the label
        label.setText("Current Year : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/41ed79611fbf18af52630859b33ad4ba.png)