# PyQt5 QCalendarWidget–获得最大高度

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-get-最大高度/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-getting-maximum-height/)

在本文中，我们将看到如何获得 QCalendarWidget 的最大高度。日历的最大高度是指在此高度之后不能再进一步扩展的高度，默认情况下，当我们在布局中创建日历时，当窗口扩展时，日历的大小也会增加，因此需要设置最大高度。我们可以借助`setMaximumHeight`设置最大高度

> 为此，我们将对 QCalendarWidget 对象使用`maximumHeight`方法。
> 
> **语法:**calendar . maximum h8()
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

        # setting maximum height of the calendar
        self.calendar.setMaximumHeight(500)

        # creating a label
        label = QLabel(self)

        # adding label to the layout
        layout.addWidget(label)

        # getting maximum height
        value = self.calendar.maximumHeight()

        # setting text to the label
        label.setText("Maximum Height  : " + str(value))

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

<video class="wp-video-shortcode" id="video-432497-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200614011841/Python-2020-06-14-01-18-18.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200614011841/Python-2020-06-14-01-18-18.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200614011841/Python-2020-06-14-01-18-18.mp4)</video>