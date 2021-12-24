# PyQt5 QCalendarWidget–设置定时器事件

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-setting-timer-event/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-timer-event/)

在本文中，我们将看到如何实现 QCalendarWidget 的计时器事件。当日历开始计时器间隔结束时，将向日历发送计时器事件。这个事件处理程序可以在一个子类中重新实现，以接收在事件参数中传递的日历 startTimer 事件。
下面是日历类代码

```
# QCalendarWidget Class
class Calendar(QCalendarWidget):

    # constructor
    def __init__(self, parent=None):
        super(Calendar, self).__init__(parent)

    # overriding the timer event
    # this will show the next month
    def timerEvent(self, event):

        # show the next month
        window.calendar.showNextMonth()
```

> 实施步骤:
> 1。创建一个继承 QCalendarWidget
> 2 的日历类。在日历类中覆盖时间显示，在事件中显示日历的下一个月
> 3。创建主窗口类
> 4。在主窗口
> 5 内创建一个日历对象。设置日历的各种属性

下面是实现

## 蟒蛇 3

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
    # this will show the next month
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

        # setting geometry to the calendar
        self.calendar.setGeometry(50, 10, 400, 250)

        # setting cursor
        self.calendar.setCursor(Qt.PointingHandCursor)

        # starting the calendar timer
        # passing 1000 milliseconds as parameter
        timer_id = self.calendar.startTimer(1000)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-430359-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200612021739/Python-2020-06-12-02-17-08.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200612021739/Python-2020-06-12-02-17-08.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200612021739/Python-2020-06-12-02-17-08.mp4)</video>