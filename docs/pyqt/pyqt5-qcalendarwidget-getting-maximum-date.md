# pyqt 5 qcalendarvdget–发布最大日期

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-get-max-date/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-getting-maximum-date/)

在本文中，我们将看到如何获得 QCalendarWidget 的最大日期。QCalendarWidget 的最大日期将用户选择限制在最大日期之上，即用户只能选择小于指定最大日期的日期。超过最大日期的日期将被禁用。我们使用 setMaximumDate 方法来设置最大日期。

> 为此，我们将对 QCalendarWidget 对象使用 maximumDate 方法。
> **语法:**calendar . maximum date()
> **参数:**不需要参数
> **返回:**返回 QDate 对象

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

        # upper bound date
        u_date = QDate(2020, 6, 15)

        # setting maximum date
        calendar.setMaximumDate(u_date)

        # creating a label
        label = QLabel(self)

        # setting geometry to the label
        label.setGeometry(100, 280, 250, 60)

        # making label multi line
        label.setWordWrap(True)

        # getting maximum date
        value = calendar.maximumDate()

        # setting text to the label
        label.setText("Maximum Date : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/1180fdf9e2f52957bc8c71807709dc70.png)