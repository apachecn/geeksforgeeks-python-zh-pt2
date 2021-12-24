# PyQt5 QCalendarWidget–获取内容矩形

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-get-content-rectangle/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-getting-content-rectangle/)

在本文中，我们将看到如何将内容矩形添加到 QCalendarWidget 中。内容矩形是内容的边框，默认情况下，内容边距值为零，因此内容矩形等于实际的边框，但是当边距改变时，它会变小，因为内容矩形是不包括边距的矩形。我们可以借助 setContentsMargins 方法添加边距。

> 为此，我们将对 QCalendarWidget 对象使用 contentsRect 方法。
> **语法:**calendar . contents rect()
> **参数:**不需要参数
> **返回:**返回 QRect 对象

下面是实现

## 蟒蛇 3

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

        # setting geometry to the calendar
        self.calendar.setGeometry(50, 10, 400, 250)

        # setting content margin
        self.calendar.setContentsMargins(40, 40, 40, 40)

        # creating a label
        label = QLabel(self)

        # setting geometry
        label.setGeometry(50, 280, 420, 120)

        # making it multi line
        label.setWordWrap(True)

        # getting content Rectangle
        value = self.calendar.contentsRect()

        # setting text to the label
        label.setText("Content Rectangle: " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/a7f4659317a4ef93191073785908c90d.png)