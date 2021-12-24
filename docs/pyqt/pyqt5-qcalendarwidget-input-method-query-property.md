# PyQt5 QCalendarWidget–输入法查询属性

> 原文:[https://www . geesforgeks . org/pyqt5-qcalendarwidget-输入法-查询-属性/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-input-method-query-property/)

在本文中，我们将看到如何将输入法查询设置为 QCalendarWidget。输入法查询属性由输入法用来查询日历的一组属性，以便能够支持复杂的输入法操作，如对周围文本和重新转换的支持。

> 为此，我们将对 QCalendarWidget 对象使用`inputMethodQuery`方法。
> 
> **语法:** calendar.inputMethodQuery(查询)
> 
> **参数:**它以 InputMethodQuery 对象为参数
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

        # setting input method query
        self.calendar.inputMethodQuery(Qt.ImEnterKeyType)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-428654-1" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200610181852/Python-2020-06-10-18-18-25.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200610181852/Python-2020-06-10-18-18-25.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200610181852/Python-2020-06-10-18-18-25.mp4)</video>