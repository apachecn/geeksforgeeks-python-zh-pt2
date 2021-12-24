# PyQt5 QCalendarWidget–使用完毕后关闭

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-使用完成时关闭/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-closing-when-use-is-done/)

在本文中，我们将看到如何关闭 QCalendarWidget。有时，在日历使用完成后，关闭日历是必要的。这可以使用 close 方法来完成，这个方法将日历发送到 QCloseEvent。

> 为此，我们将对 QCalendarWidget 对象使用 close 方法。
> **语法:** calendar.close()
> **参数:**不需要参数
> **返回:**返回 bool

下面是实现

## 蟒蛇 3

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
        self.setGeometry(100, 100, 600, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        # creating a QCalendarWidget object
        self.calendar = QCalendarWidget(self)

        # setting geometry to the calendar
        self.calendar.setGeometry(10, 10, 400, 250)

        # creating a push button
        button = QPushButton("Close", self)

        # setting geometry tot he button
        button.setGeometry(100, 280, 100, 40)

        # adding action to the button
        button.clicked.connect(self.do_action)

    # method called by push button
    def do_action(self):

        # closing the calendar
        self.calendar.close()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-421767-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200531011538/Python-2020-05-31-01-15-02.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200531011538/Python-2020-05-31-01-15-02.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200531011538/Python-2020-05-31-01-15-02.mp4)</video>