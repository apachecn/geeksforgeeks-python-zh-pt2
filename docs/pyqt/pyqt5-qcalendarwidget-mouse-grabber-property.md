# PyQt5 QCalendarWidget–鼠标抓取器属性

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendar widget-mouse-grabber-property/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-mouse-grabber-property/)

在本文中，我们将看到如何获得 QCalendarWidget 的鼠标抓取器属性。我们可以借助`mouseGrabber`方法访问鼠标抓取器属性，该方法返回当前正在抓取鼠标输入的日历或其子日历。如果此应用程序中没有小部件正在抓取鼠标，则返回 None。我们可以借助`grabMouse`方法抓取鼠标。

> 为此，我们将对 QCalendarWidget 对象使用`mouseGrabber`方法。
> 
> **语法:** calendar.mouseGrabber()
> 
> **论证:**不需要论证
> 
> **返回:**返回 QWidget 对象

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

        # grabbing the keyboard for the calendar
        self.calendar.grabKeyboard()

        # creating label to show the properties
        self.label = QLabel(self)

        # setting geometry to the label
        self.label.setGeometry(100, 280, 250, 60)

        # making label multi line
        self.label.setWordWrap(True)

        # getting mouse grabber property
        value = self.calendar.mouseGrabber()

        # setting text to the label
        self.label.setText("Calendar Mouse grabber : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/f26a81fded6bd21832a7a66231fa4e29.png)