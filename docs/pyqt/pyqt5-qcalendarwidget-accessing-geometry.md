# PyQt5 QCalendarWidget–访问几何图形

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-access-geometry/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-accessing-geometry/)

在本文中，我们将看到如何获得 QCalendarWidget 的几何图形。几何基本上是指日历的位置和大小。我们可以借助`resize`方法改变日历的大小，借助`move`方法改变位置。将这两种方法结合起来，就形成了历法的几何学。借助`setGeometry`方法，我们可以改变/设置日历的几何形状。

> 为此，我们将对 QCalendarWidget 对象使用`geometry`方法。
> 
> **语法:** calendar.geometry()
> 
> **论证:**不需要论证
> 
> **返回:**返回对象

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

        # creating label to show the properties
        self.label = QLabel(self)

        # setting geometry to the label
        self.label.setGeometry(100, 280, 250, 60)

        # making label multi line
        self.label.setWordWrap(True)

        # getting geometry
        value = self.calendar.geometry()

        # setting text to the label
        self.label.setText("Geometry : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/2600add640f29c5e5deb98694bf2786b.png)