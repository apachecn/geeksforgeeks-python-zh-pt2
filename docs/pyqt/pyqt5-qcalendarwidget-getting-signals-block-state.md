# PyQt5 QCalendarWidget–获取信号块状态

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-get-signal-block-state/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-getting-signals-block-state/)

在本文中，我们将看到如何检查与 QCalendarWidget 相关联的信号是否处于阻塞状态。有各种信号与日历相关联，例如日期变化信号、页面变化信号等。仅使用这些信号将动作添加到日历中。我们可以借助 block signals 方法来屏蔽信号。

> 为此，我们将对 QCalendarWidget 对象使用 signalsBlocked 方法。
> **语法:**日历.信号锁定()
> **参数:**不需要参数
> **返回:**返回 bool

下面是实现

## 蟒蛇 3

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
        self.setGeometry(100, 100, 600, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        # creating a QCalendarWidget object
        self.calendar = QCalendarWidget(self)

        # setting geometry to the calendar
        self.calendar.setGeometry(50, 10, 400, 250)

        # creating a label
        label = QLabel(self)

        # setting geometry
        label.setGeometry(120, 280, 200, 60)

        # making it multi line
        label.setWordWrap(True)

        # adding action to the calendar
        self.calendar.selectionChanged.connect(lambda: label.setText("Selection Changed Signal"))

        # adding action to the calendar
        self.calendar.currentPageChanged.connect(lambda: label.setText("Page Changed Signal"))

        # blocking the signals
        self.calendar.blockSignals(True)

        # getting signals blocked state
        value = self.calendar.signalsBlocked()

        # setting text to the label
        label.setText("Signals Blocked : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-424920-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200605012223/Python-2020-06-05-01-22-02.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200605012223/Python-2020-06-05-01-22-02.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200605012223/Python-2020-06-05-01-22-02.mp4)</video>