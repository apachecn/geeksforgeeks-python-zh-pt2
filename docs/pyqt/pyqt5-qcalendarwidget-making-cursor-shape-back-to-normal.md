# PyQt5 QCalendarWidget–使光标形状恢复正常

> 原文:[https://www . geesforgeks . org/pyqt5-qcalendarwidget-making-cursor-shape-恢复正常/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-making-cursor-shape-back-to-normal/)

在本文中，我们将看到如何重置 QCalendarWidget 的光标形状。光标是默认光标形状的鼠标指针，也就是说，尽管日历有各种各样的光标可用，例如，拆分光标、大小光标等，但窗口或日历的光标看起来是相同的。默认情况下，它有箭头光标，但可以通过 setCursor 方法进行更改。为了使光标恢复默认状态，我们必须取消设置特殊光标。

> 为此，我们将对 QCalendarWidget 对象使用 unsetCursor 方法。
> **语法:**calendar . unsetcursor()
> **参数:**不需要参数
> **返回:**不返回

下面是实现

## 蟒蛇 3

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

        # setting geometry to the calendar
        self.calendar.setGeometry(50, 10, 400, 250)

        # setting cursor
        self.calendar.setCursor(Qt.PointingHandCursor)

        # removing special cursor
        self.calendar.unsetCursor()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-426097-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200606000209/Python-2020-06-06-00-01-47.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200606000209/Python-2020-06-06-00-01-47.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200606000209/Python-2020-06-06-00-01-47.mp4)</video>