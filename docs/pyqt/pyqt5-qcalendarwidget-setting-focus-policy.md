# PyQt5 QCalendarWidget–设置焦点策略

> 原文:[https://www . geesforgeks . org/pyqt 5-qcalendarwidget-setting-focus-policy/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-focus-policy/)

在本文中，我们将看到如何为 QCalendarWidget 设置焦点策略。该属性保持小部件接受键盘焦点的方式，有许多焦点策略可用于日历，如无焦点、强焦点、滚轮焦点等。

> 为此，我们将对 QCalendarWidget 对象使用`setFocusPolicy`方法。
> 
> **语法:** calendar.setFocusPolicy(Qt。NoFocus)
> 
> **论证:**以聚焦政策为论证
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
        self.calender = QCalendarWidget(self)

        # setting geometry to the calender
        self.calender.setGeometry(50, 10, 400, 250)

        # setting cursor
        self.calender.setCursor(Qt.PointingHandCursor)

        # setting focus policy to calendar
        # as no focus is set keyboard input will not work
        self.calender.setFocusPolicy(Qt.NoFocus)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-426174-1" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200607022640/Python-2020-06-07-02-26-01.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200607022640/Python-2020-06-07-02-26-01.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200607022640/Python-2020-06-07-02-26-01.mp4)</video>