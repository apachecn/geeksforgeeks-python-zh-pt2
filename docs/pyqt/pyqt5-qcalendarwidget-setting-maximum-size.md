# PyQt5 QCalendarWidget–设置最大尺寸

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-setting-maximum-size/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-maximum-size/)

在本文中，我们将看到如何设置 QCalendarWidget 的最大大小。日历的最大大小是在此之后不能再进一步扩展的大小，默认情况下，当我们在布局中创建日历时，当窗口扩展或缩小时，日历的大小也会增加和缩小，因此，需要设置最大大小。我们可以分别借助`setMaximumWidth`和`setMaximumHeight`方法单独设置最大宽度和高度。

> 为此，我们将对 QCalendarWidget 对象使用`setMaximumSize`方法。
> 
> **语法:** calendar.setMaximumSize(大小)
> 
> **自变量:**它以 QSize 对象为自变量
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

        # setting maximum size
        self.calendar.setMaximumSize(QSize(500, 400))

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
![](img/64be16fdd0e8316986aa3873c0d520e6.png)

当我们尝试展开窗口时日历大小没有展开时最大大小达到
![](img/3b2d5891792dbeef0a94b46994e033f7.png)