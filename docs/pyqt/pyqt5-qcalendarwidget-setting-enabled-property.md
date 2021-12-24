# PyQt5 QcalendarWidget–设置启用属性

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-setting-enabled-property/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-enabled-property/)

在本文中，我们将看到如何将 enabled 属性设置为 QCalendarWidget。Enabled 属性保存日历是否已启用。通常，启用的日历处理键盘和鼠标事件，而禁用的日历不处理。

> 为此，我们将对 QCalendarWidget 对象使用 setEnabled 方法。
> **语法:**calendar . setenabled(False)
> **引数:**以 bool 为引数
> **返回:**不返回

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

        # setting enabled property
        self.calendar.setEnabled(False)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-429436-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200611001741/Python-2020-06-11-00-16-27.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200611001741/Python-2020-06-11-00-16-27.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200611001741/Python-2020-06-11-00-16-27.mp4)</video>