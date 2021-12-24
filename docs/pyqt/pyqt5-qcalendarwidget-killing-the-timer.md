# PyQt5 QCalendarWidget–关闭定时器

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-秒杀计时器/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-killing-the-timer/)

在本文中，我们将看到如何杀死 QCalendarWidget 的计时器。为了启动定时器，我们使用`startTimer`方法，该方法在经过一定的时间间隔后调用 timerEvent。它启动一个定时器并返回一个定时器标识符，如果不能启动定时器，则返回零。

> 为此，我们将对 QCalendarWidget 对象使用`killTimer`方法。
> 
> **语法:** calendar.killTimer(timer_id)
> 
> **自变量:**以整数为自变量，即定时器 ID
> 
> **返回:**不返回

**实施步骤::**
1。创建一个继承 QCalendarWidget
2 的日历类。在日历类中覆盖时间显示，在事件中显示日历的下一个月
3。创建主窗口类
4。在主窗口内创建一个日历对象
5。设置日历的各种属性
6。创建一个按钮
7。在按钮上添加动作，在动作中杀死计时器

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

        # setting geometry to the calender
        self.calendar.setGeometry(50, 10, 400, 250)

        # setting cursor
        self.calendar.setCursor(Qt.PointingHandCursor)

        # starting the calendar timer
        # passing 1000 milliseconds as parameter
        self.timer_id = self.calendar.startTimer(1000)

        # creating a push button
        push = QPushButton("Kill Timer", self)

        # setting geometry to the push button
        push.setGeometry(100, 280, 120, 40)

        # adding action to the push button
        push.clicked.connect(self.do_Action)

    def do_Action(self):

        # killing the timer
        self.calendar.killTimer(self.timer_id)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-430361-1" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200612022415/Python-2020-06-12-02-23-53.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200612022415/Python-2020-06-12-02-23-53.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200612022415/Python-2020-06-12-02-23-53.mp4)</video>