# pyqt 5 qcalendarvdget–设置字体

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-setting-font/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-font/)

在本文中，我们将看到如何为 QCalendarWidget 设置字体。字体是字体的特定大小、重量和样式。每种字体都是一组匹配的字体，每个字形一个。通过改变字体，我们可以改变日历中文本的样式。

> 为此，我们将对 QCalendarWidget 对象使用`setFont`方法。
> 
> **语法:** calendar.setFont(字体)
> 
> **自变量:**它以 QFont 对象为自变量
> 
> **返回:**不返回

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
        self.setGeometry(100, 100, 650, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):
        # creating a QCalendarWidget object
        self.calender = QCalendarWidget(self)

        # setting geometry to the calender
        self.calender.setGeometry(50, 10, 400, 250)

        # setting cursor
        self.calender.setCursor(Qt.PointingHandCursor)

        # font
        font = QFont('Times', 5)

        # setting font to the calendar
        self.calender.setFont(font)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-426191-1" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200608001953/Python-2020-06-08-00-19-23.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200608001953/Python-2020-06-08-00-19-23.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200608001953/Python-2020-06-08-00-19-23.mp4)</video>