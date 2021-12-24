# PyQt5 QCalendarWidget–获取对象名称属性

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-get-object-name-property/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-getting-object-name-property/)

在本文中，我们将看到如何获取 QCalendarWidget 的对象名。对象名基本上就是给日历的对象起的名字，我们可以借助对象名找到 PyQt5 应用中的对象，我们可以借助`findChild`方法找到它。我们可以借助`setObjectName`方法将对象名称设置到日历中。

> 为此，我们将对 QCalendarWidget 对象使用`objectName`方法。
> 
> **语法:** calendar.objectName()
> 
> **论证:**不需要论证
> 
> **返回:**返回字符串

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

        # setting object name of calendar
        self.calendar.setObjectName("Geek")

        # creating a label
        label = QLabel(self)

        # setting geometry to the label
        label.setGeometry(100, 280, 250, 60)

        # making label multi line
        label.setWordWrap(True)

        # getting calendar object name
        value = self.calendar.objectName()

        # setting text to the label
        label.setText("Object Name : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/441d90de8527f6dcba1a21f62cf05591.png)