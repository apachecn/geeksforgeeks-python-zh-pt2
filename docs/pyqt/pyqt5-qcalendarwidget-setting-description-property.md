# PyQt5 QCalendarWidget–设置描述属性

> 原文:[https://www . geesforgeks . org/pyqt 5-qcalendarwidget-setting-description-property/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-description-property/)

在本文中，我们将看到如何设置 QCalendarWidget 的 description 属性。Description 属性保存日历的详细信息，即日历是如何制作的以及与之相关的重要事项等所有详细信息。

> 为了做到这一点，我们将对 QCalendarWidget 对象使用 setAccessibleDescription 方法。
> **语法:**calendar . setaccessibledescription(text)
> **参数:**它以字符串作为参数
> **执行的动作:**它返回 None

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

        # setting description
        calendar.setAccessibleDescription("This is a description")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/608cdc26096e40de16d9f884ba59d278.png)