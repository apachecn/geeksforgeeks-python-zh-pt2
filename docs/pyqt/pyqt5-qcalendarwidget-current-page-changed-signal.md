# PyQt5 QCalendarWidget–当前页面已更改信号

> 原文:[https://www . geesforgeks . org/pyqt5-qcalendarwidget-current-page-changed-signal/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-current-page-changed-signal/)

在本文中，我们将看到如何从 QCalendarWidget 获取当前页面更改信号。当当前显示的月份改变时，发出当前页面改变信号。

> 为此，我们将对 QCalendarWidget 对象使用 currentPageChanged 方法。
> **语法:**calendar . currentpagechanged . connect(lambda:print(“Page Changed”))
> **参数:**它以方法作为参数
> **执行的动作:**每当发出激活信号时它就会打印消息

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

        # creating a label
        label = QLabel(self)

        # setting geometry to the label
        label.setGeometry(100, 280, 250, 60)

        # making label multi line
        label.setWordWrap(True)

        # text
        text = "Current Page hanged signal (No.) : "

        # current count
        self.count = 0

        # getting the current page change signal and
        # when receives the signal printing the message
        calendar.currentPageChanged.connect(lambda: label.setText(text + str(get_count())))

        # method to increase the count value
        def get_count():
            self.count += 1
            return self.count

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-421772-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200531014810/Python-2020-05-31-01-47-43.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200531014810/Python-2020-05-31-01-47-43.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200531014810/Python-2020-05-31-01-47-43.mp4)</video>