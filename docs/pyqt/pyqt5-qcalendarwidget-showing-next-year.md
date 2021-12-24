# pyqt 5 qcalendar widget–展示明年

> 原文:[https://www . geesforgeks . org/pyqt 5-qcalendarwidget-show-明年/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-showing-next-year/)

在本文中，我们将看到如何在屏幕上显示下一年的 QCalendarWidget。显示下一年是指相对于当前显示年份的下一年。

**注意:**所选日期不变。

> 为此，我们将对 QCalendarWidget 对象使用`showNextYear`方法。
> 
> **语法:** calendar.showNextYear()
> 
> **论证:**不需要论证
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
        self.setGeometry(100, 100, 600, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        # creating a QCalendarWidget object
        calender = QCalendarWidget(self)

        # setting geometry to the calender
        calender.setGeometry(10, 10, 400, 250)

        # creating push button
        push = QPushButton("Next Year", self)

        # setting geometry to the push
        push.setGeometry(120, 280, 100, 40)

        # adding action to the push
        push.clicked.connect(lambda: do_action())

        def do_action():
            # showing next YEAR
            calender.showNextYear()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-422417-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200602041152/Python-2020-06-02-04-11-15.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200602041152/Python-2020-06-02-04-11-15.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200602041152/Python-2020-06-02-04-11-15.mp4)</video>