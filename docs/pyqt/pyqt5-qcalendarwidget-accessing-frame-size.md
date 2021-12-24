# PyQt5 QCalendarWidget–访问帧大小

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-access-frame-size/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-accessing-frame-size/)

在本文中，我们将看到如何获得 QCalendarWidget 的帧大小。框架大小 o 保存日历的大小，包括任何窗口框架，默认情况下，该属性包含一个取决于用户平台和屏幕几何形状的值。

> 为此，我们将对 QCalendarWidget 对象使用 frameSize 方法。
> **语法:** calendar.frameSize()
> **参数:**不需要参数
> **返回:**返回 QSize 对象

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
        self.calender = QCalendarWidget(self)

        # setting geometry to the calendar
        self.calender.setGeometry(50, 10, 400, 250)

        # setting cursor
        self.calender.setCursor(Qt.PointingHandCursor)

        # creating label to show the properties
        self.label = QLabel(self)

        # setting geometry to the label
        self.label.setGeometry(100, 280, 250, 60)

        # making label multi line
        self.label.setWordWrap(True)

        # getting frame size
        value = self.calender.frameSize()

        # setting text to the label
        self.label.setText("Frame Size: " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/0c2914c449448a844d12e26b2e5e45bf.png)