# PyQt5 QCalendarWidget–改变几何图形

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-changing-geometry/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-changing-geometry/)

在本文中，我们将看到如何改变 QCalendarWidget 的几何图形。几何基本上是指日历的位置和大小。我们可以借助`resize`方法改变日历的大小，借助`move`方法改变位置。将这两种方法结合起来，就形成了历法的几何学。

> 为此，我们将对 QCalendarWidget 对象使用`setGeometry`方法。
> 
> **语法:** calendar.setGeometry(左、上、宽、高)
> 
> **自变量:**取 4 个整数作为自变量
> 
> **返回:**不返回

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
        self.calender = QCalendarWidget(self)

        # setting cursor
        self.calender.setCursor(Qt.PointingHandCursor)

        # creating a push button add action
        push = QPushButton("Set Geometry", self)

        # move the push button
        push.move(100, 280)

        # adding action to the push
        push.clicked.connect(self.push_action)

    def push_action(self):

        # setting geometry of the calendar
        self.calender.setGeometry(50, 10, 400, 250)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-426210-1" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200608033502/Python-2020-06-08-03-34-30.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200608033502/Python-2020-06-08-03-34-30.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200608033502/Python-2020-06-08-03-34-30.mp4)</video>