# PyQt5 QCalendarWidget–如何使用鼠标

将其拖放到窗口中的任何位置

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-如何使用鼠标在窗口中的任何位置拖放它/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-how-to-drag-and-drop-it-anywhere-in-the-window-using-mouse/)

在本文中，我们将看到如何在主窗口中拖放日历。为了拖动日历，用户必须点击日历的标题栏并移动光标来移动日历，为了放下，只需释放光标。

> **实施步骤:**
> 1。创建一个继承 QCalendarWidget
> 2 的日历类。在日历类内覆盖鼠标按下和释放事件，在事件内更新移动标志
> 3。创建主窗口类
> 4。创建日历对象
> 5。设置主窗口鼠标跟踪启用
> 6。覆盖鼠标移动事件
> 7。在鼠标移动事件中获得 x，y 坐标，并根据它改变日历的位置

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

    # overriding the mouse press event
    def mousePressEvent(self, QMouseEvent):

        # making flag true
        window.move_calendar = True

    # overriding the mouse release event
    def mouseReleaseEvent(self, event):

        # making flag false
        window.move_calendar = False

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

        # creating amove flag
        self.move_calendar = False

    # method for components
    def UiComponents(self):

        # creating a QCalendarWidget object
        # as Calendar class inherits QCalendarWidget
        self.calendar = Calendar(self)

        # enabling mouse tracking
        self.calendar.setMouseTracking(True)
        self.setMouseTracking(True)

        # setting geometry to the calender
        self.calendar.setGeometry(50, 10, 250, 250)

        # setting cursor
        self.calendar.setCursor(Qt.PointingHandCursor)

    # overriding the mouse move event
    def mouseMoveEvent(self, event):

        # getting x, y co-ordinates
        x = event.x()
        y = event.y()

        # checking the flag
        if self.move_calendar:

            # moving the calendar
            self.calendar.move(x, y)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-432408-1" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200613041824/Python-2020-06-13-04-17-35.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200613041824/Python-2020-06-13-04-17-35.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200613041824/Python-2020-06-13-04-17-35.mp4)</video>