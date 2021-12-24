# PyQt5 QCalendarWidget–年份旋转框的背景色

> 原文:[https://www . geeksforgeeks . org/pyqt5-qcalendarwidget-背景色-按年旋转框/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-background-color-to-the-year-spin-box/)

在本文中，我们将看到如何为 QCalendarWidget 的年份旋转框设置背景颜色。在工具按钮中的日历中有一个选择年份的旋转框，将边框设置为 QCalendarWidget 不同于将背景颜色设置为其他 Widget，日历是具有多个子组件的 widget，即我们也可以将背景颜色设置为独立组件。下面是带有背景色的日历的外观

![](img/ad3a287fa3b3b8fb116da0cac7329077.png)

为此，我们将对 QCalendarWidget 对象使用`setStyleSheet`方法，下面是样式表代码

```py
QCalendarWidget QSpinBox
{
background-color : lightgreen;
}

```

**注意:**用户可以用年份旋转框做类似的动作，可以用普通的旋转框小部件

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
        # adding background color to the calendar's spin box
        self.calendar.setStyleSheet("QCalendarWidget QSpinBox"
                                    "{"
                                    "background-color : lightgreen;"
                                    "}"
                                    )

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-434785-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200618003645/Python-2020-06-18-00-36-21.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200618003645/Python-2020-06-18-00-36-21.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200618003645/Python-2020-06-18-00-36-21.mp4)</video>