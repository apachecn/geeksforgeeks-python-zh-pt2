# PyQt5 QCalendarWidget–释放抓取的鼠标输入

> 原文:[https://www . geesforgeks . org/pyqt5-qcalendarwidget-release-抓取-鼠标-输入/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-releasing-grabbed-mouse-input/)

在本文中，我们将看到如何取消绑定，即释放 QCalendarWidget 的鼠标输入。通过抓住鼠标，日历将不会受到影响，除了它没有收到任何鼠标事件。`setFocus`照常移动焦点，但新的焦点小部件只有在调用`releaseMouse`后才接收鼠标事件。我们可以借助`grabMouse`的方法抓住老鼠。

> 为此，我们将对 QCalendarWidget 对象使用`releaseMouse`方法。
> 
> **语法:** calendar.releaseMouse()
> 
> **论证:**不需要论证
> 
> **返回:**不返回

下面是实现

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

        # setting geometry to the calender
        self.calendar.setGeometry(50, 10, 400, 250)

        # setting cursor
        self.calendar.setCursor(Qt.PointingHandCursor)

        # grabbing mouse input
        self.calendar.grabMouse()

        # releasing mouse input
        self.calendar.releaseMouse()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
鼠标和键盘输入都在工作

<video class="wp-video-shortcode" id="video-426227-1" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200608042323/Python-2020-06-08-04-22-51.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200608042323/Python-2020-06-08-04-22-51.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200608042323/Python-2020-06-08-04-22-51.mp4)</video>