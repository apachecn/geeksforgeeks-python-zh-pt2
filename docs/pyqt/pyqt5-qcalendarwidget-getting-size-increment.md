# PyQt5 QCalendarWidget–获取大小增量

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-get-size-increment/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-getting-size-increment/)

在本文中，我们将看到如何获得 QCalendarWidget 的大小增量。当日历大小随着更改主窗口大小而变化时，使用大小增量。默认情况下，对于新创建的日历，此属性包含宽度和高度为零的大小。

**注意:**大小增量在 Windows 下没有效果，在 X11 上可能会被窗口管理器忽略。

> 为此，我们将对 QCalendarWidget 对象使用`sizeIncrement`方法。
> 
> **语法:** calendar.sizeIncrement()
> 
> **论证:**不需要论证
> 
> **返回:**返回 QSize 对象

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
        self.setMouseTracking(True)

class Window(QMainWindow):

    def __init__(self):
        super().__init__()

        # setting title
        self.setWindowTitle("Python ")

        # setting geometry
        self.setGeometry(100, 100, 500, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        # creating a layout
        layout = QVBoxLayout()

        # creating a QCalendarWidget object
        # as Calendar class inherits QCalendarWidget
        self.calendar = Calendar(self)

        # setting cursor
        self.calendar.setCursor(Qt.PointingHandCursor)

        # adding calendar tot he layout
        layout.addWidget(self.calendar)

        # setting size increment
        self.calendar.setSizeIncrement(QSize(20, 20))

        # creating a label
        label = QLabel(self)

        # adding label to the layout
        layout.addWidget(label)

        # getting size increment
        value = self.calendar.sizeIncrement()

        # setting text to the label
        label.setText("Size Increment : " + str(value))

        # setting layout
        widget = QWidget()
        widget.setLayout(layout)
        self.setCentralWidget(widget)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-432435-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200614035357/Python-2020-06-14-03-53-39.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200614035357/Python-2020-06-14-03-53-39.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200614035357/Python-2020-06-14-03-53-39.mp4)</video>