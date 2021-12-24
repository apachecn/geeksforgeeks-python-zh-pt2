# pyqt 5 qcalendar 预算–发布最小日期

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-get-minimum-date/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-getting-minimum-date/)

在本文中，我们将看到如何获得 QCalendarWidget 的最小日期。QCalendarWidget 的最小日期将用户选择限制在最小日期以下，即用户只能选择大于指定最小日期的日期。低于最小日期的日期将被禁用。我们使用 setMinimumDate 方法来设置最大日期。

> 为此，我们将对 QCalendarWidget 对象使用 minimumDate 方法。
> **语法:**calendar . minimum date()
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

        # setting geometry to the calender
        calender.setGeometry(10, 10, 400, 250)

        # lower bound date
        l_date = QDate(2020, 6, 5)

        # setting minimum date
        calender.setMinimumDate(l_date)

        # creating a label
        label = QLabel(self)

        # setting geometry to the label
        label.setGeometry(100, 280, 250, 60)

        # making label multi line
        label.setWordWrap(True)

        # getting minimum date
        value = calender.minimumDate()

        # setting text to the label
        label.setText("Minimum Date : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/45266b72ecf7c0aa6a59598506c45177.png)