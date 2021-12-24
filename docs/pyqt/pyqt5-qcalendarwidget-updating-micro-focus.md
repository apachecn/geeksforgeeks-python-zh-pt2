# PyQt5 QCalendarWidget–更新微焦点

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-更新-微焦点/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-updating-micro-focus/)

在本文中，我们将看到如何更新微焦点 QCalendarWidget。有许多焦点，即焦点原因可用，如后退标签，弹出原因等。设置焦点是重载函数，我们可以通过更新来反映微焦点的变化。

> 为此，我们将对 QCalendarWidget 对象使用`updateMicroFocus`方法。
> 
> **语法:** calendar.updateMicroFocus()
> 
> **论证:**不需要论证
> 
> **返回:**返回无

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
        self.setGeometry(100, 100, 600, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        # creating a QCalendarWidget object
        calender = QCalendarWidget(self)

        # setting geometry to the calender
        calender.setGeometry(10, 10, 400, 250)

        # setting focus
        calender.setFocus(Qt.NoFocusReason)

        # updating the micro focus
        calender.updateMicroFocus()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/fc014b6d21e5fba9b49423dad0e77e9c.png)