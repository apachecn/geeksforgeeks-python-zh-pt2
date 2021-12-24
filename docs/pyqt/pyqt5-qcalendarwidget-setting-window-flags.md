# PyQt5 QCalendarWidget–设置窗口标志

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-设置-窗口-标志/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-window-flags/)

在本文中，我们将看到如何设置 QCalendarWidget 的窗口标志。窗口标志是一种类型(例如:Qt::Dialog)和零个或多个窗口系统提示(例如:Qt::frameleswindowhint)的组合。如果日历具有类型 Qt::Widget 或 Qt::SubWindow，并成为一个窗口(Qt::Window、Qt::Dialog 等)。)，则放在桌面上的位置(0，0)。如果小部件是一个窗口，并成为 Qt::小部件或 Qt::子窗口，它将被放在相对于其父小部件的位置(0，0)。

> 为此，我们将对 QCalendarWidget 对象使用`setWindowFlags`方法。
> 
> **语法:**calendar . setwindowflags(flag)
> 
> **自变量:**以窗口标志对象为自变量
> 
> **返回:**不返回

下面是实现

```py
# importing libraries
from PyQt5.QtWidgets import * 
from PyQt5 import QtCore, QtGui
from PyQt5.QtGui import * 
from PyQt5.QtCore import * 
import sys

# QCalendarWidget Class
class Calendar(QCalendarWidget):

    # constructor
    def __init__(self, parent = None):
        super(Calendar, self).__init__(parent)

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

        # creating a QCalendarWidget object
        # as Calendar class inherits QCalendarWidget
        self.calendar = Calendar(self)

        # setting cursor
        self.calendar.setCursor(Qt.PointingHandCursor)

        # setting size of the calendar
        self.calendar.resize(300, 240)

        # move the calendar
        self.calendar.move(10, 10)

        # setting windows flag
        self.calendar.setWindowFlags(Qt.SplashScreen)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/35ccc13e656d7ef7f5d7df41f9a60d89.png)