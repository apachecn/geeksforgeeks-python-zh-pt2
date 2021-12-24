# PyQt5 QcalendarWidget–使其成为活动窗口

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-making-it-active-window/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-making-it-active-window/)

在本文中，我们将看到如何使 QCalendarWidget 成为一个活动窗口。活动窗口是具有键盘输入焦点的可见顶层窗口。使其成为活动窗口会将包含此日历的顶层小部件设置为活动窗口。

**注意:**窗口必须可见，否则 activateWindow()不起作用。

> 为此，我们将对 QCalendarWidget 对象使用`activateWindow`方法。
> 
> **语法:** calendar.activateWindow()
> 
> **论证:**不需要论证
> 
> **执行的操作:**返回无

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

        # setting name
        calender.setAccessibleName("Geek Calendar")

        # making it an active window
        calender.activateWindow()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/143de558ac4d82c10e8754e1460da88a.png)