# PyQt5 QCalendarWidget–前一个月按钮的背景色

> 原文:[https://www . geeksforgeeks . org/pyqt5-qcalendarwidget-背景色-前一个月-按钮/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-background-color-to-the-previous-month-button/)

在本文中，我们将看到如何为 QCalendarWidget 的前一个月按钮设置背景颜色。“上个月”按钮在工具按钮的左边，工具按钮是顶部可用的按钮，即转到左页和右页的按钮，将背景设置为 QCalendarWidget 不同于将背景设置为其他小部件，日历是有多个子部件的小部件，即我们也可以将边框设置为独立部件。

我们可以在样式表中借助`QCalendarWidget QToolButton`作为类名来为工具按钮设置边框，但是这将为工具按钮的所有元素设置边框。

为此，我们将对 QCalendarWidget 对象使用`setStyleSheet`方法，下面是样式表代码

```
QCalendarWidget QToolButton#qt_calendar_prevmonth
{
background-color : lightgreen;
}
QCalendarWidget QToolButton#qt_calendar_prevmonth::hover
{
background-color : lightgreen;
}
QCalendarWidget QToolButton#qt_calendar_prevmonth::pressed
{
background-color : lightgreen;
}

```

**注意:**我们使用 QToolButton # Qt _ calendar _ prev month::悬停和 QToolButton # Qt _ calendar _ prev month::按下，仅当鼠标悬停在它们上方或按下它们时才添加背景颜色。也有！悬停和！按下，这是悬停和按下状态的相反状态。

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
        # adding background to the navigation  bar previous month button
        # adding background color when mouse hover over it and when it get pressed
        self.calendar.setStyleSheet("QCalendarWidget QToolButton# qt_calendar_prevmonth"
                                    "{"
                                    "background-color : lightgreen;"
                                    "}"
                                    "QCalendarWidget QToolButton# qt_calendar_prevmonth::hover"
                                    "{"
                                    "background-color : cyan;"
                                    "}"
                                    "QCalendarWidget QToolButton# qt_calendar_prevmonth::pressed"
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

**输出:**

<video class="wp-video-shortcode" id="video-434797-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200618012546/Python-2020-06-18-01-25-25.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200618012546/Python-2020-06-18-01-25-25.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200618012546/Python-2020-06-18-01-25-25.mp4)</video>