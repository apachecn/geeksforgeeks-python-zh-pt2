# PyQt5 QCalendarWidget-设置名称属性

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-setting-name-property/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-name-property/)

在本文中，我们将看到如何设置 QCalendarWidget 的 name 属性。Name 属性保存日历的名称，名称用于区分日历，即根据用途对日历进行分类，例如，出生日历、预订日历等。

> 为此，我们将对 QCalendarWidget 对象使用`setAccessibleName`方法。
> 
> **语法:** calendar.setAccessibleName(文本)
> 
> **自变量:**以字符串为自变量
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

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/908107f44a69caebe1f93d6fb289d38b.png)