# PyQt5 QCalendarWidget–分配基本大小值

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-赋值-基本大小-值/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-assigning-base-size-value/)

在本文中，我们将看到如何将基本大小值设置为 QCalendarWidget。默认情况下，基本尺寸的宽度和高度都为零，如果日历定义了尺寸增量，即当窗口尺寸改变时，其尺寸也改变，则基本尺寸用于计算合适的日历尺寸。基本大小是日历的初始大小。

> 为此，我们将对 QCalendarWidget 对象使用 setBaseSize 方法。
> **语法:** calendar.setBaseSize(宽度、高度)
> **自变量:**取两个整数作为自变量
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
        self.setGeometry(100, 100, 600, 400)

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

        # setting base size
        self.calendar.setBaseSize(400, 25)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/c1e9da6b9224ea55137976a5b3fac4d4.png)