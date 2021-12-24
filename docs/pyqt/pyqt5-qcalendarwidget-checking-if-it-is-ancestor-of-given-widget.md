# PyQt5 QCalendarWidget–检查它是否是给定 Widget 的祖先

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-检查它是否是给定 widget 的祖先/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-checking-if-it-is-ancestor-of-given-widget/)

在本文中，我们将看到如何检查 QCalendarWidget 是否是给定 Widget 的祖先。为了做到这一点，我们使用`isAncestorOf`方法，如果日历是给定子代的父代(或祖父母等到了任何级别)，并且两个小部件都在同一个窗口内，则该方法返回 true 否则返回 false。

> 为此，我们将对 QCalendarWidget 对象使用`isAncestorOf`方法。
> 
> **语法:**calendar . essoristorof(查询)
> 
> **参数:**它以 QWidget 对象为参数
> 
> **返回:**返回 bool

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
        self.calendar = QCalendarWidget(self)

        # setting geometry to the calender
        self.calendar.setGeometry(50, 10, 400, 250)

        # setting cursor
        self.calendar.setCursor(Qt.PointingHandCursor)

        # creating label to show the properties
        self.label = QLabel(self)

        # setting geometry to the label
        self.label.setGeometry(100, 280, 250, 60)

        # making label multi line
        self.label.setWordWrap(True)

        # getting third child of the calendar
        child = self.calendar.children()[3]

        # checking if the calendar is ancestor of the child
        value = self.calendar.isAncestorOf(child)

        # setting text to the label
        self.label.setText("Ancestor ? : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/277ad7bbc57bfab29712688d0b5c5ad2.png)