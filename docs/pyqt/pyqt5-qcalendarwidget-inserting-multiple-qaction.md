# PyQt5 QCalendarWidget–插入多个动作

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-insert-multi-QA action/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-inserting-multiple-qaction/)

在本文中，我们将看到如何同时向 QCalendarWidget 插入多个 QAction。为此，我们使用`insertActions`方法，该方法在给定动作之前，将动作动作插入日历的动作列表中。如果 before 为 None 或 before 不是此小部件的有效操作，它将追加操作。

> 为此，我们将对 QCalendarWidget 对象使用`InsertActions`方法。
> 
> **语法:** calendar.insertActions(之前，action_list)
> 
> **参数:**它以 QAction 对象和一个列表作为参数
> 
> **返回:**不返回

下面是实现

```py
# importing libraries
from PyQt5.QtWidgets import * 
from PyQt5 import QtCore, QtGui
from PyQt5.QtGui import * 
from PyQt5.QtCore import * 
import sys

# QCalendarWidget Class
class Calendar(QCalendarWidget):

    # constructor
    def __init__(self, parent = None):
        super(Calendar, self).__init__(parent)

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
        # as Calendar class inherits QCalendarWidget
        self.calendar = Calendar(self)

        # setting geometry to the calender
        self.calendar.setGeometry(50, 10, 400, 250)

        # setting cursor
        self.calendar.setCursor(Qt.PointingHandCursor)

        # creating a QAction objects
        action1 = QAction("Geek", self)
        action2 = QAction("Python", self)

        # creating action list
        action_list = [action1, action2]

        # adding actions to calendar
        self.calendar.addActions(action_list)

        # actions
        action_3 = QAction("BTech", self)
        action_4 = QAction("MTech", self)

        # action list
        insert_action_list = [action_3, action_4]

        # inserting action in before second action
        self.calendar.insertActions(action2, insert_action_list)

        # creating label to show the properties
        self.label = QLabel(self)

        # setting geometry to the label
        self.label.setGeometry(100, 280, 300, 100)

        # making label multi line
        self.label.setWordWrap(True)

        # getting action of the calendar
        value = self.calendar.actions()

        # setting text to the label
        self.label.setText("Actions : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/c2cd31b43d311eef80668058c9a792b3.png)