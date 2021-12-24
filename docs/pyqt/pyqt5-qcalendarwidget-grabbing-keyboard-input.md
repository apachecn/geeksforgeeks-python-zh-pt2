# PyQt5 QCalendarWidget-抓取键盘输入

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-抓取-键盘-输入/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-grabbing-keyboard-input/)

在本文中，我们将看到如何为 QCalendarWidget 获取键盘输入。通过抓取键盘，日历不会受到影响，只是它不会接收任何键盘事件。`setFocus`照常移动焦点，但新的焦点小部件只有在调用`releaseKeyboard`后才接收键盘事件。

> 为此，我们将对 QCalendarWidget 对象使用`grabKeyboard`方法。
> 
> **语法:** calendar.grabKeyboard()
> 
> **论证:**不需要论证
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

        # grabbing keyboard input
        self.calendar.grabKeyboard()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
鼠标输入正常，但键盘输入不正常

<video class="wp-video-shortcode" id="video-426221-1" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200608040029/Python-2020-06-08-03-59-44.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200608040029/Python-2020-06-08-03-59-44.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200608040029/Python-2020-06-08-03-59-44.mp4)</video>