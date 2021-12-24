# PyQt5 QCalendarWidget–Ungrab 手势属性

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-ungrab-手势-属性/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-ungrab-gesture-property/)

在本文中，我们将看到如何取消订阅给定的 QCalendarWidget 抓取手势。日历中有各种抓取手势，如点击手势、点击并按住(长按)手势、平移手势、捏手势、滑动手势和自定义手势，这些都可以使用`grabGesture`方法进行设置。

> 为此，我们将对 QCalendarWidget 对象使用`ungrabGesture`方法。
> 
> **语法:**calendar . ungrabbination(Qt。点击手势)
> 
> **自变量:**以手势标志为自变量
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
        self.calendar = QCalendarWidget(self)

        # setting geometry to the calender
        self.calendar.setGeometry(50, 10, 400, 250)

        # setting cursor
        self.calendar.setCursor(Qt.PointingHandCursor)

        # setting grab gesture
        self.calendar.grabGesture(Qt.TapGesture)

        # ungrabbing the gesture
        self.calendar.ungrabGesture(Qt.TapGesture)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/51c79e0bf72dfa4aaab922d239533e70.png)