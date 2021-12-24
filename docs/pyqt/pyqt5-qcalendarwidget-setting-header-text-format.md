# PyQt5 QCalendarWidget–设置标题文本格式

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-设置-标题-文本-格式/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-header-text-format/)

在本文中，我们将看到如何为 QCalendarWidget 的标题设置文本格式。日历有两个标题，一个显示星期几，即水平标题，另一个是显示星期几的垂直标题。设置标题文本格式意味着设置这两个标题的格式，即样式。

> 为了做到这一点，我们将对 QCalendarWidget 对象使用 setHeaderTextFormat 方法。
> **语法:**calendar . setheadertextformat(format)
> **参数:**它以 QTextCharFormat 对象作为参数
> **返回:**它不返回

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
        self.setGeometry(100, 100, 650, 400)

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

        # setting cursor
        self.calendar.setCursor(Qt.PointingHandCursor)

        # format
        format = QTextCharFormat()
        format.setFont(QFont('Times', 12))

        # setting header text format
        self.calendar.setHeaderTextFormat(format)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-427438-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200609020819/Python-2020-06-09-02-07-46.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200609020819/Python-2020-06-09-02-07-46.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200609020819/Python-2020-06-09-02-07-46.mp4)</video>