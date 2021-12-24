# PyQt5 QCalendarWidget–设置方向属性

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-setting-direction-property/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-direction-property/)

在本文中，我们将看到如何设置 QCalendarWidget 的方向。日历中有三种可用的方向，第一种是默认的从左到右，第二种是从右到左的布局，这是某些语言所必需的，尤其是阿拉伯语和希伯来语。第三是 LayoutDirectionAuto 服务于两个目的。当与其他对象结合使用时，它将意味着使用父小部件或 QApplication 上设置的布局方向。

> 为此，我们将对 QCalendarWidget 对象使用 setLayoutDirection 方法。
> **语法:** calendar.setLayoutDirection(方向)
> **自变量:**它以方向对象为自变量
> **返回:**它不返回

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

        # setting direction
        self.calendar.setLayoutDirection(Qt.RightToLeft)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/51c661b1d1894b4b9dc5700a6d933674.png)