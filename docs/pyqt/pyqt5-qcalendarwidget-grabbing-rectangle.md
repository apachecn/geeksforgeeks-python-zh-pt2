# PyQt5 QCalendarWidget–抓取矩形

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-抓取-矩形/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-grabbing-rectangle/)

在本文中，我们将看到如何从 QCalendarWidget 获取矩形。抓取矩形意味着将日历渲染成受给定矩形限制的位图。如果日历有孩子，那么他们也会被画在适当的位置。

> 为此，我们将对 QCalendarWidget 对象使用`grab`方法。
> 
> **语法:**日历.抓取(矩形)
> 
> **自变量:**它以 QRect 对象为自变量
> 
> **返回:**它返回 QPixmap 对象

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

        # rectangle
        rec = QRect(50, 10, 100, 100)

        # grab
        value = self.calendar.grab(rec)

        # setting text to the label
        self.label.setText("Pixmap : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/b09c813cc9886a32ac2e2a091381e157.png)