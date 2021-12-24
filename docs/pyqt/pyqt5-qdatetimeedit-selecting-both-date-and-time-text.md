# PyQt5 qdatetime 编辑–选择日期和时间文本

> 原文:[https://www . geesforgeks . org/pyqt 5-qdatetime edit-select-date-time-text/](https://www.geeksforgeeks.org/pyqt5-qdatetimeedit-selecting-both-date-and-time-text/)

在本文中，我们将看到如何选择 QDateTimeEdit 小部件的日期和时间文本。QDateTime 基本上是 QDate 和 QTime 的组合，即它既有日期又有时间。而 QDateTimeEdit 小部件用于显示或接收 QDateTime。所选文本可用于覆盖或移除。
为了做到这一点，我们将对 QDateTimeEdit 对象使用 selectAll 方法。

> **语法:**datetime edit . selectall()
> **参数:**不需要参数
> **返回:**返回 None

下面是实现

## 蟒蛇 3

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

        # setting date time to it
        datetimeedit.setDateTime(QDateTime(2020, 10, 10, 11, 30))

        # time
        time = QTime(21, 45)

        # setting only time
        datetimeedit.setTime(time)

        # creating a push button
        push = QPushButton("Select All", self)

        # setting geometry of the push button
        push.setGeometry(100, 150, 120, 30)

        # adding action to the push button
        # selecting all the text
        push.clicked.connect(lambda: datetimeedit.selectAll())

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-451341-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200711022928/Python-2020-07-11-02-29-09.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200711022928/Python-2020-07-11-02-29-09.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200711022928/Python-2020-07-11-02-29-09.mp4)</video>