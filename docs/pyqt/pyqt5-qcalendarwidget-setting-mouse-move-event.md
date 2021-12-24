# PyQt5 QCalendarWidget–设置鼠标移动事件

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-setting-mouse-move-event/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-mouse-move-event/)

在本文中，我们将看到如何实现 QCalendarWidget 的鼠标移动事件。对于事件事件，这个事件处理程序可以在子类中重新实现，以接收小部件的鼠标移动事件。如果关闭鼠标跟踪，只有在移动鼠标时按下鼠标按钮，才会发生鼠标移动事件。如果打开鼠标跟踪，即使没有按下鼠标按钮，也会发生鼠标移动事件。

> 实施步骤:
> 1。创建一个继承 QCalendarWidget
> 2 的日历类。创建一个标签来显示更新
> 3。覆盖 mouseMoveEvent 并将位置设置为标签
> 4。在主窗口
> 5 内创建一个日历对象。为日历设置各种属性

下面是实现

```py
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
        self.setMouseTracking(True)

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

        # turing on the mouse tracking
        self.setMouseTracking(True)

        # setting geometry to the calender
        self.calendar.setGeometry(50, 10, 250, 250)

        # setting cursor
        self.calendar.setCursor(Qt.PointingHandCursor)

        # creating label to show the properties
        self.label = QLabel(self)

        # setting geometry to the label
        self.label.setGeometry(100, 280, 250, 60)

        # making label multi line
        self.label.setWordWrap(True)

    def mouseMoveEvent(self, event):
        self.label.setText('coords: ( % d : % d )' % (event.x(), event.y()))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-432493-1" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200613040837/Python-2020-06-13-04-08-14.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200613040837/Python-2020-06-13-04-08-14.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200613040837/Python-2020-06-13-04-08-14.mp4)</video>