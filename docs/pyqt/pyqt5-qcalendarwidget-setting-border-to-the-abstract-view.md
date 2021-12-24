# PyQt5 QCalendarWidget–设置抽象视图的边框

> 原文:[https://www . geeksforgeeks . org/pyqt5-qcalendarwidget-设置-边框到摘要-视图/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-border-to-the-abstract-view/)

在本文中，我们将看到如何为 QCalendarWidget 的抽象视图设置边框。在日历中，抽象视图是由其中的日期组成的视图，将边框设置为 QCalendarWidget 不同于将边框设置为其他小部件，日历是有多个子部件的小部件，即我们也可以将边框设置为独立的部件。

为此，我们将对 QCalendarWidget 对象使用`setStyleSheet`方法，下面是样式表代码

```py
QCalendarWidget QAbstractItemView
{
border : 4px solid green;
}

```

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
        self.calendar.resize(350, 240)

        # move the calendar
        self.calendar.move(10, 10)

        # setting stylesheet
        # adding border to the abstract view
        self.calendar.setStyleSheet("QCalendarWidget QAbstractItemView"
                                    "{"
                                    "border : 4px solid green;"
                                    "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/0c266700e3e66006f66bf31da47c2569.png)