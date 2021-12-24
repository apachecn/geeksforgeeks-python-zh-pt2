# PyQt5 QCalendarWidget–设置标题

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-setting-title/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-title/)

在本文中，我们将看到如何设置 QCalendarWidget 的标题。标题基本上是 QCalendarWidget 的标题，标题基本上是日历的名称或小提示。

> 为此，我们将对 QCalendarWidget 对象使用`setWindowTitle`方法。
> 
> **语法:** calendar.setWindowTitle(文本)
> 
> **自变量:**以字符串为自变量
> 
> **返回:**返回无

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
        self.setGeometry(100, 100, 600, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        # creating a QCalendarWidget object
        calender = QCalendarWidget(self)

        # setting geometry to the calender
        calender.setGeometry(10, 10, 400, 250)

        # title
        title = "Calendar PyQt5"

        # setting title i.e caption
        calender.setWindowTitle(title)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/1933d7558c90a3abfb3d5f67fb67a802.png)