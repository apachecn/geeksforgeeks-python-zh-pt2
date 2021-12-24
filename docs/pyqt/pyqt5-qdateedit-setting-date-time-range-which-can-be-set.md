# PyQt5 qdate edit–设置可设置的日期时间范围

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdate edit-setting-date-time-range-哪些可以设置/](https://www.geeksforgeeks.org/pyqt5-qdateedit-setting-date-time-range-which-can-be-set/)

在本文中，我们将看到如何设置 QDateEdit 的日期时间范围。通过设置日期时间范围，我们将设置日期时间的下限和上限绑定到日期编辑。我们可以借助`setDateTime`方法将日期时间设置为日期编辑。最小日期时间和最大日期时间可以分别通过`setMinimumDateTime`和`setMaximumDateTime`方法设置到日期编辑中。

为了做到这一点，我们对 QDateEdit 对象使用`setDateTimeRange`方法

> **语法:** date.setDateTimeRange(最小，最大)
> 
> **参数:**它以两个 QDateTime 对象作为参数
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

        # creating a QDateEdit widget
        date = QDateEdit(self)

        # setting geometry of the date edit
        date.setGeometry(100, 100, 200, 40)

        # alignment
        a_flag = Qt.AlignCenter

        # setting alignment of date
        date.setAlignment(a_flag)

        # QDate object
        d1 = QDateTime(2020, 1, 1, 10, 30)
        d2 = QDateTime(2031, 1, 1, 11, 10)

        # setting date time range
        date.setDateTimeRange(d1, d2)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-445982-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200704034055/Python-2020-07-04-03-40-36.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200704034055/Python-2020-07-04-03-40-36.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200704034055/Python-2020-07-04-03-40-36.mp4)</video>