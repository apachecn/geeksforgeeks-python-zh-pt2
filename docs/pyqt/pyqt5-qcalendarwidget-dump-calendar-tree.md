# PyQt5 QCalendarWidget–转储日历树

> 原文:[https://www . geesforgeks . org/pyqt5-qcalendarwidget-dump-calendar-tree/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-dump-calendar-tree/)

在本文中，我们将看到如何转储 QCalendarWidget 的对象树，转储日历树意味着将子树转储到调试输出。对象树是一种树形数据结构，在节点处保存日历的子对象。

> 为此，我们将对 QCalendarWidget 对象使用 dumpObjectTree 方法。
> **语法:**calendar . dumpobjecttree()
> **参数:**不需要参数
> **返回:**不返回

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
        self.calendar = QCalendarWidget(self)

        # setting geometry to the calendar
        self.calendar.setGeometry(50, 10, 400, 250)

        # setting cursor
        self.calendar.setCursor(Qt.PointingHandCursor)

        # dumping the object tree
        self.calendar.dumpObjectTree()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()
window.calendar.destroy()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/eef9515e397c75562fbb98f1c04c51aa.png)