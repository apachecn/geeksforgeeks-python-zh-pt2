# PyQt5 QCalendarWidget–下个月按钮的背景色

> 原文:[https://www . geeksforgeeks . org/pyqt5-qcalendarwidget-背景色-下个月-按钮/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-background-color-of-the-next-month-button/)

在本文中，我们将看到如何为 QCalendarWidget 的下个月按钮设置背景色。下个月按钮在工具按钮的右边尺寸，工具按钮是顶部可用的按钮，即进入左和右页面的按钮，将背景颜色设置为 QCalendarWidget 不同于将背景颜色设置为其他小部件，日历是有多个子部件的小部件，即我们也可以将边框设置为独立部件。

我们可以在样式表中借助`QCalendarWidget QToolButton`作为类名来为工具按钮设置背景色，但是这将为工具按钮的所有元素设置背景色。

为此，我们将对 QCalendarWidget 对象使用`setStyleSheet`方法，下面是样式表代码

```py
QCalendarWidget QToolButton#qt_calendar_nextmonth
{
background-color : lightgreen;
}
QCalendarWidget QToolButton#qt_calendar_nextmonth::hover
{
background-color : cyan;
}
QCalendarWidget QToolButton#qt_calendar_nextmonth::pressed
{
background-color : red;
}

```

**注意:**我们使用 QToolButton # Qt _ calendar _ next month::悬停和 QToolButton # Qt _ calendar _ next month::按下，仅当鼠标悬停在它们上面或按下它们时才添加背景色。也有！悬停和！按下，这是悬停和按下状态的相反状态。

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
        # adding background to the navigation  bar next month button
        # adding background color when mouse hover over it and when it get pressed
        self.calendar.setStyleSheet("QCalendarWidget QToolButton# qt_calendar_nextmonth"
                                    "{"
                                    "background-color : lightgreen;"
                                    "}"
                                    "QCalendarWidget QToolButton# qt_calendar_nextmonth::hover"
                                    "{"
                                    "background-color : cyan;"
                                    "}"
                                    "QCalendarWidget QToolButton# qt_calendar_nextmonth::pressed"
                                    "{"
                                    "background-color : red;"
                                    "}"
                                    )

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

输出:

<video class="wp-video-shortcode" id="video-434799-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200618010948/Python-2020-06-18-01-08-43.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200618010948/Python-2020-06-18-01-08-43.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200618010948/Python-2020-06-18-01-08-43.mp4)</video>