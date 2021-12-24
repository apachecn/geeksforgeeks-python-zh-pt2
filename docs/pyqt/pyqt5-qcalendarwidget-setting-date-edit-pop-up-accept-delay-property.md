# PyQt5 QCalendarWidget–设置日期编辑(弹出)接受延迟属性

> 原文:[https://www . geesforgeks . org/pyqt 5-qcalendarwidget-设置-日期-编辑-弹出-接受-延迟-属性/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-date-edit-pop-up-accept-delay-property/)

在本文中，我们将看到如何设置/更改 QCalendarWidget 的日期编辑接受延迟属性。此属性保存非活动日期编辑在内容被接受之前显示的时间。如果启用了日历小部件的日期编辑，此属性指定在最近一次用户输入后日期编辑保持打开的时间(以毫秒为单位)。一旦这段时间过去，日期编辑中指定的日期被接受，弹出窗口关闭。默认情况下，延迟定义为 1500 毫秒(1.5 秒)。

当我们尝试使用键盘选择时，会出现日期编辑弹出窗口，延迟弹出窗口的值越小，关闭得越快

> 为此，我们将对 QCalendarWidget 对象使用 setDateEditAcceptDelay 方法。
> **语法:**calendar . setdate editaccept delay(n)
> **参数:**取整数参数
> **返回:**不返回

下面是实现

## 蟒蛇 3

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

        # setting cursor
        self.calendar.setCursor(Qt.PointingHandCursor)

        # removing special cursor
        self.calendar.unsetCursor()

        # setting accept delay value
        self.calendar.setDateEditAcceptDelay(2000)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-426099-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200606004546/Python-2020-06-06-00-45-17.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200606004546/Python-2020-06-06-00-45-17.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200606004546/Python-2020-06-06-00-45-17.mp4)</video>