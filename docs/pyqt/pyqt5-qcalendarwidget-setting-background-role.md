# PyQt5 QCalendarWidget–设置背景角色

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-设置-背景-角色/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-background-role/)

在本文中，我们将看到如何为 QCalendarWidget 设置背景角色。背景角色定义日历调色板中用于渲染背景的画笔。如果未设置明确的背景角色，日历将继承其父小部件的背景角色。

> 为此，我们将对 QCalendarWidget 对象使用 setBackgroundRole 方法。
> **语法:**calendar . setbackgroundrole(palette _ object)
> **参数:**取 QPalette。ColorRole 对象参数
> **返回:**它不返回

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
        self.setGeometry(100, 100, 600, 400)

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

        # enabling auto fill background
        self.calendar.setAutoFillBackground(True)

        # setting background role
        self.calendar.setBackgroundRole(QPalette.Base)

        # getting palette and setting color to the background to it
        p = self.calendar.palette()
        p.setColor(self.calendar.backgroundRole(), Qt.yellow)
        self.calendar.setPalette(p)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/8d774730d493605352160bfc658c0db9.png)