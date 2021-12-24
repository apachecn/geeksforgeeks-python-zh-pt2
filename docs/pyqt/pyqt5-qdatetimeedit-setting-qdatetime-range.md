# PyQt5 QDateTimeEdit – 设置 QDateTime Range

> 原文:[https://www . geesforgeks . org/pyqt 5-qdatetime edit-setting-qdatetime-range/](https://www.geeksforgeeks.org/pyqt5-qdatetimeedit-setting-qdatetime-range/)

在本文中，我们将看到如何设置 QDateTimeEdit 小部件的 QDateTime 范围。QDateTime 基本上是 QDate 和 QTime 的组合，即它既有日期又有时间。而 QDateTimeEdit 小部件用于显示或接收 QDateTime。我们可以在`setDateTime`的帮助下设置日期时间。通过设置范围，确保允许用户输入给定范围内的日期时间，我们可以分别借助`setMinimumDateTime`和`setMinimumDateTime`方法设置最小和最大日期时间。

为了做到这一点，我们将使用`setDateTimeRange`方法和 QDateTimeEdit 对象。

> **语法:**datetimeedit . setdatetimer range(最小值、最大值)
> 
> **参数:**它以两个 QDateTime 对象作为参数
> 
> **返回:**返回无

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
        self.setGeometry(100, 100, 500, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        # creating a QDateTimeEdit widget
        datetimeedit = QDateTimeEdit(self)

        # setting geometry
        datetimeedit.setGeometry(100, 100, 150, 35)

        # date time
        dt1 = QDateTime(2020, 10, 10, 11, 30)
        dt2 = QDateTime(2020, 10, 20, 22, 40)

        # setting minimum date time to it
        datetimeedit.setDateTimeRange(dt1, dt2)

        # creating a label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry to the label
        label.setGeometry(100, 160, 200, 60)

        # making label multi line
        label.setWordWrap(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-451355-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200711030300/Python-2020-07-11-03-02-30.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200711030300/Python-2020-07-11-03-02-30.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200711030300/Python-2020-07-11-03-02-30.mp4)</video>