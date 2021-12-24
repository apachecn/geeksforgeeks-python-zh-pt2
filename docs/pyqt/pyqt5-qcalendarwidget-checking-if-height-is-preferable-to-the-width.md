# PyQt5 QCalendarWidget–检查高度是否优于宽度

> 原文:[https://www . geesforgeks . org/pyqt5-qcalendarwidget-检查高度是否优于宽度/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-checking-if-height-is-preferable-to-the-width/)

在本文中，我们将看到如何根据宽度来检查 QCalendarWidget 的高度是否更好。优选高度意味着高度取决于宽度。取决于宽度的高度意味着当宽度改变时，高度也随之改变。默认情况下，高度不取决于宽度。

> 为此，我们将对 QCalendarWidget 对象使用`hasHeightForWidth`方法。
> 
> **语法:**calendar . HasheightForWhidth()
> 
> **论证:**不需要论证
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

        # creating label to show the properties
        self.label = QLabel(self)

        # setting geometry to the label
        self.label.setGeometry(100, 280, 250, 60)

        # making label multi line
        self.label.setWordWrap(True)

        # checking height for width
        value = self.calendar.hasHeightForWidth()

        # setting text to the label
        self.label.setText("Height for width : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/78457cace632182d5175354a2ab63942.png)