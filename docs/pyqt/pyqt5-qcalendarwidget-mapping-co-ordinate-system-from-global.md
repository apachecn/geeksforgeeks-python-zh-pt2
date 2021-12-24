# PyQt5 QCalendarWidget–从全球

映射坐标系统

> 原文:[https://www . geeksforgeeks . org/pyqt5-qcalendarwidget-mapping-co-cool-system-from-global/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-mapping-co-ordinate-system-from-global/)

在本文中，我们将看到如何从全局将坐标系映射到 QCalendarWidget。为此，我们使用`mapFromGlobal`方法，将全局屏幕坐标位置转换为日历坐标..

> 为此，我们将对 QCalendarWidget 对象使用`mapFromGlobal`方法。
> 
> **语法:** calendar.mapFromGlobal(点)
> 
> **自变量:**它以 QPoint 对象为自变量
> 
> **返回:**返回 QPoint 对象

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
        self.setGeometry(100, 100, 650, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        # creating a QCalendarWidget object
        # as Calendar class inherits QCalendarWidget
        self.calendar = Calendar(self)

        # setting geometry to the calender
        self.calendar.setGeometry(50, 10, 400, 250)

        # setting cursor
        self.calendar.setCursor(Qt.PointingHandCursor)

        # creating label to show the properties
        self.label = QLabel(self)

        # setting geometry to the label
        self.label.setGeometry(100, 280, 250, 60)

        # making label multi line
        self.label.setWordWrap(True)

        # mapping to widget co-ordinate system from global
        value = self.calendar.mapFromGlobal(QPoint(50, 10))

        # setting text to the label
        self.label.setText("Mapped Point from Global : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/5f7ab624ac3dafbee30cf9a26fa93564.png)