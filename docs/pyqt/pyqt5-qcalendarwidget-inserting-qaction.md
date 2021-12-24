# pyqt 5 qcalendarwdget–插入 qation

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-inserting-QA action/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-inserting-qaction/)

在本文中，我们将看到如何将 QAction 插入到 QCalendarWidget 中。为了做到这一点，我们使用`insertAction`方法，该方法在给定动作之前，将该动作插入日历的动作列表中。如果 before 为 None 或 before 不是此小部件的有效操作，它将追加操作。

> 为此，我们将对 QCalendarWidget 对象使用`insertAction`方法。
> 
> **语法:** calendar.insertAction(在，Action 之前)
> 
> **自变量:**它以两个 qaaction 对象作为自变量作为自变量，第一个是已经添加的 qaaction，第二个是将被插入到‘before’qaaction 之前的 qaaction
> 
> **返回:**不返回

下面是实现

```
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

        # 3 rd action
        action_mid = QAction("BTech", self)

        # inserting action in before second action
        self.calendar.insertAction(action2, action_mid)

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
![](img/238e30ba1ad81fe28fdd2593e09e51e1.png)