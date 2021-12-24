# PyQt5 QCalendarWidget–将焦点放在前一个子代上

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-making-focus-to-previous-child/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-making-focus-to-previous-child/)

在本文中，我们将看到如何将焦点从 QCalendarWidget 转移到上一个小部件。为了做到这一点，我们使用`focusPreviousChild`方法。它会找到一个新的小部件来赋予键盘焦点，就像 Shift+Tab 一样，如果能找到新的小部件，它会返回 true，如果找不到，它会返回 false。

> 为此，我们将对 QCalendarWidget 对象使用`focusPreviousChild`方法。
> 
> **语法:** calendar.focusPreviousChild()
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
        self.calender = QCalendarWidget(self)

        # setting geometry to the calender
        self.calender.setGeometry(50, 10, 400, 250)

        # setting cursor
        self.calender.setCursor(Qt.PointingHandCursor)

        # creating label to show the properties
        self.label = QLabel(self)

        # setting geometry to the label
        self.label.setGeometry(100, 280, 250, 60)

        # making label multi line
        self.label.setWordWrap(True)

        # focus previous child
        value = self.calender.focusPreviousChild()

        # setting text to the label
        self.label.setText("Found focus on previous ? : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/c218b0ae00199843a0e85e86383d2137.png)