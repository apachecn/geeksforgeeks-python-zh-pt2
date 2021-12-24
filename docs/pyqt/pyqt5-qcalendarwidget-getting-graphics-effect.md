# PyQt5 QCalendarWidget–获得图形效果

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-get-graphics-effect/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-getting-graphics-effect/)

在本文中，我们将看到如何获得 QCalendarWidget 的图形效果。图形效果是可以在精灵或舞台上使用的效果，以某种方式改变它们的外观。图形效果可以是彩色阴影任何东西。可以借助`setGraphicsEffect`方法设置为日历。

> 为此，我们将对 QCalendarWidget 对象使用`graphicsEffect`方法。
> 
> **语法:** calendar.graphicsEffect()
> 
> **论证:**不需要论证
> 
> **返回:**它返回 QGraphicEffect 对象

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

        # creating a color graphic effect
        color = QGraphicsColorizeEffect()
        color.setColor(Qt.green)

        # setting graphics to the calendar
        self.calendar.setGraphicsEffect(color)

        # creating label to show the properties
        self.label = QLabel(self)

        # setting geometry to the label
        self.label.setGeometry(100, 280, 250, 60)

        # making label multi line
        self.label.setWordWrap(True)

        # getting graphics effect
        value = self.calendar.graphicsEffect()

        # setting text to the label
        self.label.setText("Effect : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/136514a8f2342c28931a7c8cac0514bd.png)