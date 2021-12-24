# PyQt5 QCalendarWidget–设置鼠标跟踪属性

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-setting-mouse-tracking-property/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-mouse-tracking-property/)

在本文中，我们将看到如何为 QCalendarWidget 设置鼠标跟踪属性。如果禁用鼠标跟踪(默认)，日历将仅在移动鼠标时按下至少一个鼠标按钮时接收鼠标移动事件。如果启用了鼠标跟踪，即使没有按下任何按钮，日历也会接收到鼠标移动事件。

> 为此，我们将对 QCalendarWidget 对象使用`setMouseTracking`方法。
> 
> **语法:**日历. setMouseTracking(真)
> 
> **自变量:**它以布尔为自变量
> 
> **返回:**不返回

下面是实现

```py
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

        # enabling mouse tracking
        self.calendar.setMouseTracking(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-427428-1" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200609014919/Python-2020-06-09-01-48-44.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200609014919/Python-2020-06-09-01-48-44.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200609014919/Python-2020-06-09-01-48-44.mp4)</video>