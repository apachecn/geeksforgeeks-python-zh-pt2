# PyQt5 QCalendarWidget–更改光标形状

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-changing-cursor-shape/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-changing-cursor-shape/)

在本文中，我们将看到如何更改 QCalendarWidget 的光标形状。光标是默认光标形状的鼠标指针，也就是说，尽管日历有各种各样的光标可用，例如，拆分光标、大小光标等，但窗口或日历的光标看起来是相同的。

> 为此，我们将对 QCalendarWidget 对象使用`setCursor`方法。
> 
> **语法:** calendar.setCursor(Qt。PointingHandCursor)
> 
> **参数:**取 QCursor 对象参数
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
        self.calender = QCalendarWidget(self)

        # setting geometry to the calender
        self.calender.setGeometry(50, 10, 400, 250)

        # setting cursor
        self.calender.setCursor(Qt.PointingHandCursor)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-426093-1" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200605234525/Python-2020-06-05-23-44-39.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200605234525/Python-2020-06-05-23-44-39.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200605234525/Python-2020-06-05-23-44-39.mp4)</video>