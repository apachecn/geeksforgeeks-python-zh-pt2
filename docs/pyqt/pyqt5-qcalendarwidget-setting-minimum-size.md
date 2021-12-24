# PyQt5 QCalendarWidget–设置最小尺寸

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-setting-minimum-size/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-minimum-size/)

在本文中，我们将看到如何设置 QCalendarWidget 的最小大小。日历的最小尺寸是指在此之后不能再缩小的尺寸，默认情况下，当我们在布局中创建日历时，当窗口扩展或缩小时，日历尺寸也会增加和缩小，因此，需要设置最小尺寸。我们可以分别借助`setMinimumWidth`和`setMinimumHeight`方法单独设置最小宽度和高度。

> 为此，我们将对 QCalendarWidget 对象使用`setMinimumSize`方法。
> 
> **语法:** calendar.setMinimumSize(大小)
> 
> **自变量:**它以 QSize 对象为自变量
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

# QCalendarWidget Class
class Calendar(QCalendarWidget):

    # constructor
    def __init__(self, parent = None):
        super(Calendar, self).__init__(parent)
        self.setMouseTracking(True)

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

        # creating a layout
        layout = QVBoxLayout()

        # creating a QCalendarWidget object
        # as Calendar class inherits QCalendarWidget
        self.calendar = Calendar(self)

        # setting cursor
        self.calendar.setCursor(Qt.PointingHandCursor)

        # adding calendar tot he layout
        layout.addWidget(self.calendar)

        # setting minimum size
        self.calendar.setMinimumSize(QSize(400, 400))

        # setting layout
        widget = QWidget()
        widget.setLayout(layout)
        self.setCentralWidget(widget)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/b37223cbfa12f51d9f49733d872a72d2.png)

当我们尝试收缩小部件时，日历在最小尺寸值
![](img/7de97eaf5eaadd4fd2eb87eb7252c68e.png)后不收缩