# PyQt5 QCalendarWidget–设置日期文本格式

> 原文:[https://www . geesforgeks . org/pyqt5-qcalendarwidget-设置-日期-文本-格式/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-date-text-format/)

在本文中，我们将看到如何在 QCalendarWidget 中将日期文本格式设置为特定日期。设置日期文本格式使指定的日期看起来更加特殊，例如增加大小和其他功能。下面是带有日期文本格式的日期的外观。

![](img/e49b73165011468fb7f7518766ffa3a0.png)

> 为此，我们将对 QCalendarWidget 对象使用`setDateTextFormat`方法。
> 
> **语法:** calendar.setDateTextFormat(日期，格式)
> 
> **参数:**需要两个参数第一个是 QDate 对象，第二个是 QTextCharFormat 对象
> 
> **返回:**不返回

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

        # format
        format = QTextCharFormat()
        format.setFont(QFont('Times', 15))

        # date
        date = QDate(2020, 6, 10)

        # setting date text format
        self.calender.setDateTextFormat(date, format)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/007b42573254498fc0126dfa9b871826.png)