# PyQt5 QCalendarWidget–设置开始计时器

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-setting-start-timer/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-start-timer/)

在本文中，我们将看到如何设置 QCalendarWidget 的启动计时器。为了做到这一点，我们使用`startTimer`方法，该方法在经过一定的时间间隔后调用 timerEvent。它启动一个定时器并返回一个定时器标识符，如果不能启动定时器，则返回零。

> 为此，我们将对 QCalendarWidget 对象使用`startTimer`方法。
> 
> **语法:** calendar.startTimer(毫秒)
> 
> **自变量:**以整数为自变量，即以毫秒为单位的间隔时间
> 
> **返回:**返回整数

**注意:**为了使用开始计时器，我们必须覆盖计时器

下面是实现

```
# importing libraries
from PyQt5.QtWidgets import * 
from PyQt5 import QtCore, QtGui
from PyQt5.QtGui import * 
from PyQt5.QtCore import * 
import sys

# QCalendarWidget Class
class Calendar(QCalendarWidget):

    # constructor
    def __init__(self, parent = None):
        super(Calendar, self).__init__(parent)

    # overriding the timer event
    def timerEvent(self, event):

        # show the next month
        window.calendar.showNextMonth()

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
        # as Calendar class inherits QCalendarWidget
        self.calendar = Calendar(self)

        # setting geometry to the calender
        self.calendar.setGeometry(50, 10, 400, 250)

        # setting cursor
        self.calendar.setCursor(Qt.PointingHandCursor)

        # starting the calendar timer
        # passing 1000 milliseconds as parameter
        timer_id = self.calendar.startTimer(1000)

        # creating label to show the properties
        self.label = QLabel(self)

        # setting geometry to the label
        self.label.setGeometry(100, 280, 250, 60)

        # making label multi line
        self.label.setWordWrap(True)

        # setting text to the label
        self.label.setText("Timer ID : " + str(timer_id))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-430357-1" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200612015630/Python-2020-06-12-01-56-09.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200612015630/Python-2020-06-12-01-56-09.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200612015630/Python-2020-06-12-01-56-09.mp4)</video>