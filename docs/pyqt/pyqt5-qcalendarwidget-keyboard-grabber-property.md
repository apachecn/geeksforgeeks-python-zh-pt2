# PyQt5 QCalendarWidget–键盘抓取器属性

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendar widget-keyboard-grabber-property/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-keyboard-grabber-property/)

在本文中，我们将看到如何获得 QCalendarWidget 的键盘抓取器属性。我们可以借助`keyboardGrabber`方法访问键盘抓取器属性，该方法返回当前正在抓取键盘输入的日历或其子日历。如果此应用程序中没有小部件正在抓取键盘，则返回无。我们可以借助`grabKeyborad`方法抓取键盘。

> 为此，我们将对 QCalendarWidget 对象使用`keyboardGrabber`方法。
> 
> **语法:** calendar.keyboardGrabber()
> 
> **论证:**不需要论证
> 
> **返回:**返回 QWidget 对象

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

        # getting keyboard grabber property
        value = self.calendar.keyboardGrabber()

        # setting text to the label
        self.label.setText("Calendar Keyboard grabber : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/1ab9977b63feae96817b3516a82ccfde.png)