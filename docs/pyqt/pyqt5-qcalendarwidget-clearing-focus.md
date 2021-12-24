# PyQt5 QCalendarWidget–清除焦点

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-clearing-focus/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-clearing-focus/)

在本文中，我们将看到如果 QCalendarWidget 有焦点，我们如何清除它的焦点。设置焦点基本上是设置焦点原因有很多焦点原因可用，如后退标签，弹出原因等。设置焦点是重载函数。我们使用`setFocus`方法将焦点设置到日历上。

> 为此，我们将对 QCalendarWidget 对象使用`clearFocus`方法。
> 
> **语法:** calendar.childFocus()
> 
> **论证:**不需要论证
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

        # setting focus
        self.calender.setFocus(Qt.NoFocusReason)

        # clearing the focus
        self.calender.clearFocus()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/505f20c706e3ae0e0459243293ad47e0.png)