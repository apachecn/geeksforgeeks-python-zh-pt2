# PyQt5 QCalendarWidget–设置关闭事件

> 原文:[https://www . geesforgeks . org/pyqt 5-qcalendarwidget-setting-close-event/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-close-event/)

在本文中，我们将看到如何实现 QCalendarWidget 的关闭事件。当 Qt 从窗口系统接收到一个日历的窗口关闭请求时，这个事件处理程序被给定的事件调用。默认情况下，事件被接受，日历关闭。我们可以重新实现这个功能来改变小部件响应窗口关闭请求的方式。

下面是日历类代码

```
# QCalendarWidget Class
class Calendar(QCalendarWidget):

    # constructor
    def __init__(self, parent=None):
        super(Calendar, self).__init__(parent)

    # overriding the closeEvent method
    def closeEvent(self, event):

        # setting text to the label
        print("Close Event Called")

```

> 实施步骤:
> 1。创建一个继承 QCalendarWidget
> 2 的日历类。在日历类中覆盖 closeEvent，在事件中打印文本
> 3。创建主窗口类
> 4。在主窗口
> 5 内创建一个日历对象。设置日历的各种属性
> 6。关闭日历

下面是实现

```
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

    # overriding the closeEvent method
    def closeEvent(self, event):

        # setting text to the label
        print("Close Event Called")

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
        # as Calendar class inherits QCalendarWidget
        self.calendar = Calendar(self)

        # setting geometry to the calender
        self.calendar.setGeometry(50, 10, 400, 250)

        # setting cursor
        self.calendar.setCursor(Qt.PointingHandCursor)

        # close the calendar
        self.calendar.close()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

```
Close Event Called
```

![](img/29dfe1956bb05bb30476ef0b479ea651.png)