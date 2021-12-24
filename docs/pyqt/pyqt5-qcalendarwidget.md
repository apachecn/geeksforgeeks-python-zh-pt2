# pyqt 5–qcalendarvdget

> 哎哎哎::1230【https://www . geeksforgeeks . org/pyqt 5-qcalendarwdget/

**QCalendarWidget** 是提供基于月的日历 Widget 的类，允许用户选择日期，这个类属于 QWidgets 类。日历是一种为了社会、宗教、商业或行政目的组织日子的系统。这是通过给时间段命名来完成的，通常是天、周、月和年。日期是在这样一个系统中指定的一个特定的日子。下面是 **QCalendarWidget** 的样子。

![](img/3e0cb355a3cc056fa5083285f4d976b0.png)

**示例:**
一个有 QCalendarWidget 的窗口，用户可以看到各个月份，可以选择任意日期
下面是实现方式

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
        calendar.setGeometry(50, 50, 400, 250)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

**<video class="wp-video-shortcode" id="video-422457-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200530000646/Python-2020-05-30-00-06-16.mp4?_=1">[https://media . geekesforgeks . org/WP-content/uploads/20200530000646/Python-2020-05-30-00-06-16 . MP4](https://media.geeksforgeeks.org/wp-content/uploads/20200530000646/Python-2020-05-30-00-06-16.mp4)</video>**