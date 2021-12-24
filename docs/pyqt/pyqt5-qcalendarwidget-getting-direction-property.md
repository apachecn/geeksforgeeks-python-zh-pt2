# PyQt5 QCalendarWidget–获取方向属性

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-get-direction-property/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-getting-direction-property/)

在本文中，我们将看到如何获得 QCalendarWidget 的方向。日历中有三种可用的方向，第一种是默认的从左到右，第二种是从右到左的布局，这是某些语言所必需的，尤其是阿拉伯语和希伯来语。第三是 LayoutDirectionAuto 服务于两个目的。当与其他对象结合使用时，它将意味着使用父小部件或 QApplication 上设置的布局方向。

> 为此，我们将对 QCalendarWidget 对象使用`layoutDirection`方法。
> 
> **语法:** calendar.layoutDirection()
> 
> **论证:**不需要论证
> 
> **返回:**它返回方向对象，但打印时显示与之相关的值

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

        # getting layout direction
        value = self.calendar.layoutDirection()

        # setting text to the label
        self.label.setText("Layout Direction : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/64aa1d20c6a1b18cb36629984400b155.png)