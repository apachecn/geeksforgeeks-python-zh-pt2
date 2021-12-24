# PyQt5 QcalendarWidget–检查它是否对其祖先

启用

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-检查其祖先是否启用/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-checking-if-it-is-enabled-to-its-ancestor/)

在本文中，我们将看到如何检查 QCalendarWidget 是否对其祖先启用。为了做到这一点，我们使用`isEnabledTo`方法。如果启用了祖先，此日历将被启用，则此方法返回 true 否则返回 false。尽管我们可以借助`setEnabled`方法更改启用属性，但默认情况下，日历对其所有父日历都是启用的。

> 为此，我们将对 QCalendarWidget 对象使用`isEnabledTo`方法。
> 
> **语法:** calendar.isEnabledTo(父)
> 
> **参数:**它以 QWidget 对象为参数
> 
> **返回:**返回 bool

下面是实现

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

        # setting geometry to the calender
        self.calendar.setGeometry(50, 10, 400, 250)

        # setting cursor
        self.calendar.setCursor(Qt.PointingHandCursor)

        # setting enabled property
        self.calendar.setEnabled(False)

        # creating label to show the properties
        self.label = QLabel(self)

        # setting geometry to the label
        self.label.setGeometry(100, 280, 250, 60)

        # making label multi line
        self.label.setWordWrap(True)

        # checking if the calendar is enabled to main window
        value = self.calendar.isEnabledTo(self)

        # setting text to the label
        self.label.setText("Enabled to main window : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/4f12c1052a9eaf743d9e240200591eb3.png)