# pyqt 5 qdatetimeedit–设置最大 QDateTime

> 原文:[https://www . geesforgeks . org/pyqt 5-qdatetime edit-setting-maximum-qdatetime/](https://www.geeksforgeeks.org/pyqt5-qdatetimeedit-setting-maximum-qdatetime/)

在本文中，我们将看到如何为 QDateTimeEdit 小部件设置最大 QDateTime。QDateTime 基本上是 QDate 和 QTime 的组合，即它既有日期又有时间。而 QDateTimeEdit 小部件用于显示或接收 QDateTime。我们可以在`setDateTime`的帮助下设置日期时间。通过设置最大值，确保不允许用户输入超过最大日期时间的日期时间。

为了做到这一点，我们将使用`setMaximumDateTime`方法和 QDateTimeEdit 对象。

> **语法:**datetimeedit . setmaximumatetime(dt)
> 
> **参数:**它以 QDateTime 对象为参数
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
        dt = QDateTime(2020, 10, 10, 11, 30)

        # setting maximum date time to it
        datetimeedit.setMaximumDateTime(dt)

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

<video class="wp-video-shortcode" id="video-451343-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200711024103/Python-2020-07-11-02-40-29.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200711024103/Python-2020-07-11-02-40-29.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200711024103/Python-2020-07-11-02-40-29.mp4)</video>