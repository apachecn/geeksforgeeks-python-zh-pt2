# PyQt5 QCalendarWidget–设置选定日期

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-设置-选定-日期/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-selected-date/)

在本文中我们将看到如何设置 QCalendarWidget 的选定日期，选定日期是当前高亮显示的日期用户可以使用鼠标和光标更改选定日期默认情况下选定日期是实时日期虽然我们可以随时设置选定日期。
**注意:**所选日期必须在最小日期和最大日期属性指定的日期范围内。

> 为此，我们将对 QCalendarWidget 对象使用 setSelectedDate 方法。
> **语法:**calendar . setselecteddate(date)
> **参数:**它以 QDate 对象为参数
> **返回:**它返回 None

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

        # date
        date = QDate(2021, 1, 1)

        # setting selected date
        calendar.setSelectedDate(date)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/c7ab725f820f0f28ffaad12f4a0d849d.png)