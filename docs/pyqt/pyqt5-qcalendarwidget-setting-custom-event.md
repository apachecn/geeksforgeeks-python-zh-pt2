# PyQt5 QCalendarWidget–设置自定义事件

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-设置-自定义-事件/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-custom-event/)

在本文中，我们将看到如何实现 QCalendarWidget 的自定义事件。这个事件处理程序可以在子类中重新实现，以接收自定义事件。自定义事件是用户定义的事件，其类型值至少与量化事件::类型枚举的量化事件::用户项一样大，并且通常是量化事件子类。

下面是日历类代码

```
# QCalendarWidget Class
class Calendar(QCalendarWidget):

    # constructor
    def __init__(self, parent=None):
        super(Calendar, self).__init__(parent)

    # overriding the customEvent method
    def customEvent(self, event):

        print("Custom Event")

```

> 实施步骤:
> 1。创建一个继承 QCalendarWidget
> 2 的日历类。在日历类中覆盖客户事件，在事件中打印文本
> 3。创建主窗口类
> 4。在主窗口
> 5 内创建一个日历对象。设置日历的各种属性
> 6。将信号连接到自定义事件

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

    # overriding the customEvent method
    def customEvent(self, event):

        print("Custom Event")

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

        # close the calendar
        self.calendar.selectionChanged.connect(lambda : self.calendar.customEvent("Change"))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-432468-1" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200613001846/Python-2020-06-13-00-18-09.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200613001846/Python-2020-06-13-00-18-09.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200613001846/Python-2020-06-13-00-18-09.mp4)</video>

```
Custom Event
Custom Event
Custom Event
Custom Event

```