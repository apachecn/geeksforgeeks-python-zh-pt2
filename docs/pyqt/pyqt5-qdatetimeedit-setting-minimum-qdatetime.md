# PyQt5 QDateTimeEdit – 设置最小 QDateTime

> 原文:[https://www . geesforgeks . org/pyqt 5-qdatetime edit-setting-minimum-qdatetime/](https://www.geeksforgeeks.org/pyqt5-qdatetimeedit-setting-minimum-qdatetime/)

在本文中，我们将看到如何设置 QDateTimeEdit 小部件的最小 QDateTime。QDateTime 基本上是 QDate 和 QTime 的组合，即它既有日期又有时间。而 QDateTimeEdit 小部件用于显示或接收 QDateTime。我们可以在`setDateTime`的帮助下设置日期时间。通过设置最小值，确保不允许用户输入低于最小日期时间的日期时间。

为了做到这一点，我们将使用`setMinimumDateTime`方法和 QDateTimeEdit 对象。

> **语法:**datetimeedit . setminimumatetime(dt)
> 
> **参数:**取 QDateTime 对象参数
> 
> **返回:**返回无

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

        # setting minimum date time to it
        datetimeedit.setMinimumDateTime(dt)

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

<video class="wp-video-shortcode" id="video-451347-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200711024958/Python-2020-07-11-02-49-26.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200711024958/Python-2020-07-11-02-49-26.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200711024958/Python-2020-07-11-02-49-26.mp4)</video>