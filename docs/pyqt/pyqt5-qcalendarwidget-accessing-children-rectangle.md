# PyQt5 QCalendarWidget–访问子矩形

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-access-children-rectangle/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-accessing-children-rectangle/)

在本文中，我们将看到如何获得 QCalendarWidget 的子矩形。日历不是一个单独的小部件，它是许多小部件的混合物，我们称之为日历的孩子。有许多子视图，如表视图、项目委托等。，我们用孩子的方法得到它的所有孩子。子矩形是除隐藏子矩形之外的所有子矩形的边界矩形。

> 为此，我们将对 QCalendarWidget 对象使用 childrenRect 方法。
> **语法:**calendar . children rect()
> **参数:**不需要参数
> **返回:**返回 QRect 对象

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

        # creating a label
        label = QLabel(self)

        # setting geometry
        label.setGeometry(50, 280, 420, 120)

        # making it multi line
        label.setWordWrap(True)

        # getting children rectangle
        value = self.calendar.childrenRect()

        # setting text to the label
        label.setText("Children Rectangle : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/ead97a6875d47c5f989d4b9b5399608b.png)