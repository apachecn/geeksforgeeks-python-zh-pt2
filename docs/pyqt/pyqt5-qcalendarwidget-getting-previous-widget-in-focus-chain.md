# PyQt5 QCalendarWidget–获取焦点链中的上一个 widget

> 原文:[https://www . geeksforgeeks . org/pyqt5-qcalendarwidget-get-previous-widget-in-focus-chain/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-getting-previous-widget-in-focus-chain/)

在本文中，我们将看到如何在 QCalendarWidget 的焦点链中获得上一个小部件。焦点链是窗口中出现的小部件/子部件的列表，它们告诉焦点的顺序，焦点链中的第一个项目将首先接收焦点。

> 为此，我们将对 QCalendarWidget 对象使用`previousInFocusChain`方法。
> 
> **语法:**calendar . previousenfocuschain()
> 
> **论证:**不需要论证
> 
> **返回:**返回 QWidget 对象

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
        self.setGeometry(100, 100, 500, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        # creating a QCalendarWidget object
        # as Calendar class inherits QCalendarWidget
        self.calendar = Calendar(self)

        # setting cursor
        self.calendar.setCursor(Qt.PointingHandCursor)

        # setting size of the calendar
        self.calendar.resize(300, 240)

        # move the calendar
        self.calendar.move(10, 10)

        # creating a label
        label = QLabel(self)

        # setting geometry to the label
        label.setGeometry(100, 280, 250, 60)

        # making label multi line
        label.setWordWrap(True)

        # getting the previous widget in focus change
        value = self.calendar.previousInFocusChain()

        # setting text to the label
        label.setText("Previous  Widget in Focus Chain : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/a1dd23308211004df3d4ccbed0e82d92.png)