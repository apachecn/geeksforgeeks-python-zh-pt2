# PyQt5 QCalendarWidget–通过禁用

停止功能

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-通过禁用停止功能/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-stopping-functions-by-disabling/)

在本文中，我们将看到如何停止 QCalendarWidget 的功能。停止功能意味着 QCalendarWidget 将不能做任何事情，如选择更改日期等。禁用日历不会从屏幕上删除或隐藏小部件。禁用用于阻止用户对其进行任何更改。

> 为此，我们将对 QCalendarWidget 对象使用 setDisabled 方法。
> **语法:**日历. setDisabled(True)
> **参数:**以 bool 为参数
> **返回:**不返回

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
        calendar = QCalendarWidget(self)

        # setting geometry to the calendar
        calendar.setGeometry(10, 10, 400, 250)

        # disabling the calendar
        calendar.setDisabled(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-421848-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200601024732/Python-2020-06-01-02-46-14.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200601024732/Python-2020-06-01-02-46-14.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200601024732/Python-2020-06-01-02-46-14.mp4)</video>