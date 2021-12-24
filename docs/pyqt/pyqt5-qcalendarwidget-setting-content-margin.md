# PyQt5 QCalendarWidget–设置内容边距

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-设置-内容-边距/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-content-margin/)

在本文中，我们将看到如何为 QCalendarWidget 设置内容边距。默认情况下，内容边距值为零。边距是内容和外部部分之间的额外空间，边距给了外部部分一些空间。

> 为此，我们将对 QCalendarWidget 对象使用 setContentsMargins 方法。
> **语法:** calendar.setContentsMargins(上、右、下、左)
> **自变量:**取四个整数作为自变量
> **返回:**不返回

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

        # setting content margin
        self.calendar.setContentsMargins(40, 40, 40, 40)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/8a541c96992141982624cd18fd48c2d7.png)