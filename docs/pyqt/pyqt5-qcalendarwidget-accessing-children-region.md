# PyQt5 QCalendarWidget–访问子区域

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-access-children-region/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-accessing-children-region/)

在本文中，我们将看到如何获得 QCalendarWidget 的子区域。日历不是一个单独的小部件，它是许多小部件的混合物，我们称之为日历的孩子。有许多子视图，如表视图、项目委托等，我们使用 children 方法来获取它的所有子视图。子区域是除隐藏子区域(即所有小部件的组合区域)之外的所有子区域(占用区域)。

> 为此，我们将对 QCalendarWidget 对象使用 childrenRegion 方法。
> **语法:**calendar . children region()
> **参数:**不需要参数
> **返回:**返回 QRegion 对象

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

        # getting children region
        value = self.calendar.childrenRegion()

        # setting text to the label
        label.setText("Children Region : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/0dc05b16cab79fe94020a7188722b081.png)