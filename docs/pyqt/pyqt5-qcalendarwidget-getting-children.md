# PyQt5 QCalendarWidget–获取孩子

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-get-children/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-getting-children/)

在本文中，我们将看到如何获得 QCalendarWidget 的子代。日历不是一个单独的小部件，它是许多小部件的混合物，我们称之为日历的孩子。有许多子视图，如表视图、项目委托等。

> 为此，我们将使用 QCalendarWidget 对象的子方法。
> **语法:** calendar.childAt()
> **参数:**不需要参数
> **返回:**返回 calendar 所有子对象的列表

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

        # getting children
        value = self.calendar.children()

        # setting text to the label
        label.setText("Children : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/8fcb75fc3c08408744d830285e854055.png)