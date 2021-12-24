# PyQt5 QCalendarWidget–访问框架几何图形

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-access-frame-geometry/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-accessing-frame-geometry/)

在本文中，我们将看到如何获得 QCalendarWidget 的框架几何。日历相对于其父框架(包括任何窗口框架)的框架几何，默认情况下，此属性包含一个取决于用户平台和屏幕几何的值。

> 为此，我们将对 QCalendarWidget 对象使用`frameGeometry`方法。
> 
> **语法:** calendar.frameGeometry()
> 
> **论证:**不需要论证
> 
> **返回:**返回对象

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
        self.calender = QCalendarWidget(self)

        # setting geometry to the calender
        self.calender.setGeometry(50, 10, 400, 250)

        # setting cursor
        self.calender.setCursor(Qt.PointingHandCursor)

        # creating label to show the properties
        self.label = QLabel(self)

        # setting geometry to the label
        self.label.setGeometry(100, 280, 250, 60)

        # making label multi line
        self.label.setWordWrap(True)

        # getting frame geometry
        value = self.calender.frameGeometry()

        # setting text to the label
        self.label.setText("Frame Geometry : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/47988c5f0ad250a0bcf22ffcffe722df.png)