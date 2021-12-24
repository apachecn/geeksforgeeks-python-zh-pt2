# PyQt5 QCalendarWidget–显示今天的日期

> 原文:[https://www . geesforgeks . org/pyqt5-qcalendarwidget-show-today-date/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-showing-today-date/)

在本文中，我们将看到如何在 QCalendarWidget 中向屏幕显示今天的日期。显示今天的日期意味着显示当前日期，即日、月和年，而不管所选日期或日历当前在哪个页面。默认情况下，日历显示今天的日期。

> 为此，我们将对 QCalendarWidget 对象使用 showToday 方法。
> **语法:** calendar.showToday()
> **参数:**不需要参数
> **返回:**返回 None

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

        # creating push button
        push = QPushButton("Today", self)

        # setting geometry to the push
        push.setGeometry(120, 280, 100, 40)

        # adding action to the push
        push.clicked.connect(lambda: do_action())

        def do_action():
            # showing the today's date
            calendar.showToday()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-422425-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200602042835/Python-2020-06-02-04-28-00.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200602042835/Python-2020-06-02-04-28-00.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200602042835/Python-2020-06-02-04-28-00.mp4)</video>