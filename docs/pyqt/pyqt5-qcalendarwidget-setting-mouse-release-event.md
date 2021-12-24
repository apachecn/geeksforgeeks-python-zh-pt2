# PyQt5 QCalendarWidget–设置鼠标释放事件

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-setting-mouse-release-event/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-mouse-release-event/)

在本文中，我们将看到如何实现 QCalendarWidget 的鼠标释放事件。对于事件，这个事件处理程序可以在子类中重新实现，以接收日历的鼠标释放事件。

下面是日历类代码

```
# QCalendarWidget Class
class Calendar(QCalendarWidget):

    # constructor
    def __init__(self, parent=None):
        super(Calendar, self).__init__(parent)

    # overriding the mouseReleaseEvent method
    def mouseReleaseEvent(self, event):
        print("Mouse Release Event")

```

> 实施步骤:
> 1。创建一个继承 QCalendarWidget
> 2 的日历类。在日历类中覆盖鼠标释放事件，在事件中打印文本
> 3。创建主窗口类
> 4。在主窗口
> 5 内创建一个日历对象。为日历设置各种属性

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

    # overriding the mousePressEvent method
    def mousePressEvent(self, event):
        print("Mouse Press Event")

    # overriding the mousePressEvent method
    def mouseReleaseEvent(self, event):
        print("Mouse Release Event")

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

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-432472-1" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200613004623/Python-2020-06-13-00-46-07.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200613004623/Python-2020-06-13-00-46-07.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200613004623/Python-2020-06-13-00-46-07.mp4)</video>

```
Mouse Press Event
Mouse Release Event
Mouse Press Event
Mouse Release Event
Mouse Press Event
Mouse Release Event

```