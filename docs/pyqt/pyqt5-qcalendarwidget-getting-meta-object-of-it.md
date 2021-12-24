# PyQt5 QCalendarWidget–获取它的元对象

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-get-meta-of-object-it/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-getting-meta-object-of-it/)

在本文中，我们将看到如何获得 QCalendarWidget 的元对象。元对象包含继承 QObject 的类的信息，例如类名、超类名、属性、信号和槽。每个包含 Q_OBJECT 宏的 QObject 子类都有一个元对象。

> 为此，我们将对 QCalendarWidget 对象使用`metaObject`方法。
> 
> **语法:** calendar.metaObject()
> 
> **论证:**不需要论证
> 
> **返回:**它返回 QMetaObject

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
        self.setMouseTracking(True)

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

        # setting geometry to the calendar
        self.calendar.setGeometry(20, 20, 300, 240)

        # creating a label
        label = QLabel(self)

        # setting geometry to the label
        label.setGeometry(100, 280, 300, 60)

        # creating label multi line
        label.setWordWrap(True)

        # getting meta object of calendar
        value = self.calendar.metaObject()

        # setting text to the label
        label.setText(str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/52499b62463185c2ab216c54b1bd5840.png)