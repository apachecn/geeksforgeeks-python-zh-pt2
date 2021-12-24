# PyQt5 QCalendarWidget–阻止所有动作(信号)

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-blocking-all-actions-signal/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-blocking-all-actions-signals/)

在本文中，我们将了解如何阻止所有与 QCalendarWidget 相关的信号。有各种信号与日历相关联，例如日期变化信号、页面变化信号等。动作被添加到日历中，仅使用此信号。

> 为此，我们将对 QCalendarWidget 对象使用 blockSignals 方法。
> **语法:**calendar . block signals(True)
> **引数:**以 bool 为引数
> **返回:**返回 bool 即日历的前一个 block 信号状态

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
        self.calendar.setGeometry(50, 10, 400, 250)

        # creating a label
        label = QLabel(self)

        # setting geometry
        label.setGeometry(120, 280, 200, 60)

        # making it multi line
        label.setWordWrap(True)

        # adding action to the calendar
        self.calendar.selectionChanged.connect(lambda: label.setText("Selection Changed Signal"))

        # adding action to the calendar
        self.calendar.currentPageChanged.connect(lambda: label.setText("Page Changed Signal"))

        # blocking the signals
        self.calendar.blockSignals(True)

        # setting text to the label
        label.setText("If signal will be emitted they will be shown here")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-424914-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200605011615/Python-2020-06-05-01-15-47.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200605011615/Python-2020-06-05-01-15-47.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200605011615/Python-2020-06-05-01-15-47.mp4)</video>