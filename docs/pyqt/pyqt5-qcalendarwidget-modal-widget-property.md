# PyQt5 QCalendarWidget–模态 Widget 属性

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-modal-widget-property/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-modal-widget-property/)

在本文中，我们将看到如何获得模态小部件属性 QCalendarWidget。为了做到这一点，我们使用`isModal`方法，这个属性保存日历是否是模态小部件。此属性仅对 windows 有意义。模态小部件阻止所有其他窗口中的小部件获得任何输入。默认情况下，此属性为 false。

> 为此，我们将对 QCalendarWidget 对象使用`isModal`方法。
> 
> **语法:** calendar.isModal()
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

        # checking if the calendar is modal
        value = self.calendar.isModal()

        # setting text to the label
        self.label.setText("Modal Calendar : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/b86a6104f49959af9cf2aa98d1a81e3c.png)