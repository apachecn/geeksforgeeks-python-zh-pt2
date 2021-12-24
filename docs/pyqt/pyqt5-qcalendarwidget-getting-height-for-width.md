# PyQt5 QCalendarWidget–获取宽度的高度

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-以高换宽/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-getting-height-for-width/)

在本文中，我们将看到如何获得 QCalendarWidget 的高度和宽度。如果日历有布局，默认实现返回布局的首选高度。如果没有布局，默认实现返回-1，表示首选高度不依赖于宽度。

> 为此，我们将对 QCalendarWidget 对象使用`heightForWidth`方法。
> 
> **语法:**calendar . height forward th(宽度)
> 
> **自变量:**以整数为自变量
> 
> **返回:**返回整数

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

        # getting height for width
        value = self.calendar.heightForWidth(400)

        # setting text to the label
        self.label.setText("Height for width  : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/c795e4174eef4010ad21330cc2e8a83f.png)