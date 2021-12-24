# PyQt5 QCalendarWidget–将皮肤设置到月菜单

> 原文:[https://www . geeksforgeeks . org/pyqt5-qcalendarwidget-设置-皮肤到月菜单/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-skin-to-the-month-menu/)

在本文中，我们将看到如何为 QCalendarWidget 的月份菜单设置皮肤。月菜单是日历的 QMenu 对象子对象，当用户按下月名时出现，以便用户选择月份，将皮肤设置为 QCalendarWidget 不同于将皮肤设置为其他小部件，日历是有多个子组件的小部件，即我们也可以将皮肤设置为独立组件。皮肤基本上是背景图像，它根据地方的大小来调整大小

为此，我们将对 QCalendarWidget 对象使用 set 样式表方法，下面是样式表代码

```py
QCalendarWidget QMenu
{
border-image : url(image.png);
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
        # adding skin to the months menu
        self.calendar.setStyleSheet("QCalendarWidget QMenu"
                                    "{"
                                    "background-image : url(image.png);"
                                    "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/9d3b7499e36a12565b9dddf98d4e015a.png)