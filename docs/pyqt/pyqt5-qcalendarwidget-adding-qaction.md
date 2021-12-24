# PyQt5 QcalendarWidget–添加动作

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-add-QA action/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-adding-qaction/)

在本文中，我们将看到如何将 QAction 添加到 QCalendarWidget 中。为了做到这一点，我们使用`addAction`方法，该方法将动作附加到日历的动作列表中。我们可以借助`actions`方法得到所有的动作。

> 为此，我们将对 QCalendarWidget 对象使用`addAction`方法。
> 
> **语法:** calendar.addAction(动作)
> 
> **自变量:**它以 QAction 对象为自变量
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

        # creating a QAction object
        action = QAction("Geek", self)

        # adding action to calendar
        self.calendar.addAction(action)

        # creating label to show the properties
        self.label = QLabel(self)

        # setting geometry to the label
        self.label.setGeometry(100, 280, 250, 60)

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
![](img/a89a69fd6fefe7880a7de2afefe53c51.png)