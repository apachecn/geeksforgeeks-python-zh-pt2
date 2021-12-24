# PyQt5 QCalendarWidget–获得最小尺寸

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-get-mini-size/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-getting-minimum-size/)

在本文中，我们将看到如何获得 QCalendarWidget 的最小大小。日历的最小尺寸是指在此之后不能再缩小的尺寸，默认情况下，当我们在布局中创建日历时，当窗口扩展或缩小时，日历尺寸也会增加和缩小，因此，需要设置最小尺寸。我们可以分别借助`setMinimumWidth`和`setMinimumHeight`方法单独设置最小宽度和高度。我们可以借助`setMinimumSize`方法设置最小尺寸。

> 为此，我们将对 QCalendarWidget 对象使用`minimumSize`方法。
> 
> **语法:** calendar.minimumSize()
> 
> **论证:**不需要论证
> 
> **返回:**返回 QSize 对象

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

        # creating a label
        label = QLabel(self)

        # adding label to the layout
        layout.addWidget(label)

        # getting minimum size
        value = self.calendar.minimumSize()

        # setting text to the label
        label.setText("Minimum Size : " + str(value))

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

<video class="wp-video-shortcode" id="video-432418-1" width="640" height="572" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200614023917/Python-2020-06-14-02-38-43.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200614023917/Python-2020-06-14-02-38-43.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200614023917/Python-2020-06-14-02-38-43.mp4)</video>