# PyQt5 QCalendarWidget–设置按键释放事件

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-设置-按键-释放-事件/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-key-release-event/)

在本文中，我们将看到如何实现 QCalendarWidget 的密钥发布事件。为了设置按键释放事件，我们必须重写 key release event 方法，通过重写按键释放事件，我们可以在释放按键时向日历添加功能。与按键事件不同，按键释放事件发生在被按下的按键被释放时，我们可以说第一次按键事件发生，然后释放事件发生

> 实施步骤:
> 1。创建主窗口
> 2。创建一个 QCalendarWidget
> 3。将各种属性设置到日历
> 4。覆盖按键释放事件
> 5。在覆盖方法中，检查是否按了 escape 键，然后隐藏日历

下面是实现

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

        # setting geometry to the calender
        self.calendar.setGeometry(50, 10, 400, 250)

        # setting cursor
        self.calendar.setCursor(Qt.PointingHandCursor)

    # overriding key release event
    def keyReleaseEvent(self, e):

        # when escape key is released
        if e.key() == Qt.Key_Escape:

            # hide the calendar
            self.calendar.hide()
            print("Escape key released Hide the calendar")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-429446-1" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200611013345/Python-2020-06-11-01-33-16.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200611013345/Python-2020-06-11-01-33-16.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200611013345/Python-2020-06-11-01-33-16.mp4)</video>

```
Escape key released Hide the calendar
```