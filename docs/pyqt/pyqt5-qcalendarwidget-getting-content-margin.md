# PyQt5 QCalendarWidget–获取内容余量

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-get-content-margin/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-getting-content-margin/)

在本文中，我们将看到如何获得 QCalendarWidget 的内容边距。默认情况下，内容边距值为零。边距是内容和外部部分之间的额外空间，边距给了外部部分一些空间。我们可以借助 setContentsMargins 方法为日历设置/添加边距。

> 为此，我们将对 QCalendarWidget 对象使用 contentsMargins 方法。
> **语法:**calendar . contents margins()
> **参数:**不需要参数
> **返回:**返回 QMargins 对象

下面是实现

## 蟒蛇 3

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

        # getting content margin
        value = self.calendar.contentsMargins()

        # setting text to the label
        label.setText("Content Margins : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/ebf29c1b9d58870cc5a16f29a045824e.png)