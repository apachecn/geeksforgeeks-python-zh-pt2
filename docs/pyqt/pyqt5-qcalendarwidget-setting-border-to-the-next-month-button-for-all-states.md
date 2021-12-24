# PyQt5 QCalendarWidget–为所有状态将边框设置为下个月按钮

> 原文:[https://www . geeksforgeeks . org/pyqt5-qcalendarwidget-设置-下一个月的边框-所有州的按钮/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-border-to-the-next-month-button-for-all-states/)

在本文中，我们将看到如何为 QCalendarWidget 的下个月按钮设置边框。下个月按钮在工具按钮的右边，工具按钮是顶部可用的按钮，也就是说，可以进入左右页面的按钮，将边框设置为 QCalendarWidget 不像将边框设置为其他 Widget，calendar 是有多个子组件的 widget，也就是说，我们可以将边框设置为独立组件。

我们可以在样式表中借助`QCalendarWidget QToolButton`作为类名来为工具按钮设置边框，但是这将为工具按钮的所有元素设置边框。

为此，我们将对 QCalendarWidget 对象使用`setStyleSheet`方法，下面是样式表代码

```py
QCalendarWidget QToolButton#qt_calendar_nextmonth
{
border : 4px solid red;
}
QCalendarWidget QToolButton#qt_calendar_nextmonth::hover
{
border : 4px solid green;
}
QCalendarWidget QToolButton#qt_calendar_nextmonth::pressed
{
border : 4px solid blue;
}

```

**注意:**我们使用 QToolButton # Qt _ calendar _ next month::悬停和 QToolButton # Qt _ calendar _ next month::按下，仅当鼠标悬停在它们上方或按下它们时才添加边框。也有！悬停和！按下，这是悬停和按下状态的相反状态。

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
        # adding border to the navigation  bar next month button
        # adding border when mouse hover over it and when it get pressed
        self.calendar.setStyleSheet("QCalendarWidget QToolButton# qt_calendar_nextmonth"
                                    "{"
                                    "border : 4px solid red;"
                                    "}"
                                    "QCalendarWidget QToolButton# qt_calendar_nextmonth::hover"
                                    "{"
                                    "border : 4px solid green;"
                                    "}"
                                    "QCalendarWidget QToolButton# qt_calendar_nextmonth::pressed"
                                    "{"
                                    "border : 4px solid blue;"
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

<video class="wp-video-shortcode" id="video-434793-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200617234228/Python-2020-06-17-23-42-00.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200617234228/Python-2020-06-17-23-42-00.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200617234228/Python-2020-06-17-23-42-00.mp4)</video>