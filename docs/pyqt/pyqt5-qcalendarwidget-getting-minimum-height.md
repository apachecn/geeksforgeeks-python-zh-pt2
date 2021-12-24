# PyQt5 QCalendarWidget–获得最小高度

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-get-minimum-height/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-getting-minimum-height/)

在本文中，我们将看到如何获得 QCalendarWidget 的最小高度。日历的最小高度是指在此高度之后不能再进一步缩小的高度，默认情况下，当我们在布局内创建日历时，当窗口变大或变小时，日历的大小也会增大或缩小，因此，需要设置最小高度。我们可以借助`setMinimumHeight`方法设置日历的最小高度。

> 为此，我们将对 QCalendarWidget 对象使用`minimumHeight`方法。
> 
> **语法:** calendar.minimumHeight()
> 
> **论证:**不需要论证
> 
> **返回:**返回整数

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

        # setting minimum height of the calendar
        self.calendar.setMinimumHeight(400)

        # creating a label
        label = QLabel(self)

        # adding label to the layout
        layout.addWidget(label)

        # getting minimum height
        value = self.calendar.minimumHeight()

        # setting text to the label
        label.setText("Minimum Height : " + str(value))

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
![](img/8c59e82ed9b92e1b6c0a81feb79ea1af.png)