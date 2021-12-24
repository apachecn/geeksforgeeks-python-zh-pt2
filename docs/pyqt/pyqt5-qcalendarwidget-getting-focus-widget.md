# PyQt5 QCalendarWidget–获取焦点 Widget

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-get-focus-widget/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-getting-focus-widget/)

在本文中，我们将看到如何获得 QCalendarWidget 的焦点小部件。焦点小部件是`setFocus`被调用的日历的最后一个子部件。对于顶级小部件，这是在该窗口被激活的情况下获得焦点的小部件

> 为此，我们将对 QCalendarWidget 对象使用`focusWidget`方法。
> 
> **语法:** calendar.focusWidget()
> 
> **论证:**不需要论证
> 
> **返回:**返回子对象

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
        self.calender = QCalendarWidget(self)

        # setting geometry to the calender
        self.calender.setGeometry(50, 10, 400, 250)

        # setting cursor
        self.calender.setCursor(Qt.PointingHandCursor)

        # getting child
        child = self.calender.children()[3]

        # setting focus reason to the child
        child.setFocus(Qt.NoFocusReason)

        # creating label to show the properties
        self.label = QLabel(self)

        # setting geometry to the label
        self.label.setGeometry(100, 280, 250, 60)

        # making label multi line
        self.label.setWordWrap(True)

        # getting focus widget 
        value = self.calender.focusWidget()

        # setting text to the label
        self.label.setText("Focus widget : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/52f3a28ebb2e3cc672a11ef1d9499950.png)