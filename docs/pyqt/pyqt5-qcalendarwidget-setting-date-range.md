# PyQt5 QCalendarWidget–设置日期范围

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-setting-date-range/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-date-range/)

在本文中，我们将看到如何将日期范围设置为 QCalendarWidget。QCalendarWidget 的日期范围限制用户选择，即用户只能选择指定日期范围内的日期。其余日期被禁用。

> 为此，我们将对 QCalendarWidget 对象使用 setDateRange 方法。
> **语法:**calendar . setdate range(lower _ date，upper_date)
> **自变量:**它以两个 QDate 对象作为自变量
> **返回:**它不返回

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

        # lower bound date
        l_date = QDate(2020, 6, 5)

        # upper bound date
        u_date = QDate(2020, 6, 15)

        # setting date range
        calendar.setDateRange(l_date, u_date)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-421795-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200601022017/Python-2020-06-01-02-19-50.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200601022017/Python-2020-06-01-02-19-50.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200601022017/Python-2020-06-01-02-19-50.mp4)</video>