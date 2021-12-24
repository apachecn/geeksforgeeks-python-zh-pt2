# PyQt5 QCalendarWidget–设置最小日期

> 原文:[https://www . geesforgeks . org/pyqt 5-qcalendarwidget-setting-minimum-date/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-minimum-date/)

在本文中，我们将看到如何为 QCalendarWidget 设置最小日期。QCalendarWidget 的最小日期将用户选择限制在最小日期以下，即用户只能选择大于指定最小日期的日期。低于最小日期的日期将被禁用。

> 为了做到这一点，我们将对 QCalendarWidget 对象使用 setMinimumDate 方法。
> **语法:**calendar . setminimumdate(date)
> **参数:**它以 QDate 对象为参数
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

        # setting minimum date
        calendar.setMinimumDate(l_date)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-421797-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200601022751/Python-2020-06-01-02-27-13.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200601022751/Python-2020-06-01-02-27-13.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200601022751/Python-2020-06-01-02-27-13.mp4)</video>