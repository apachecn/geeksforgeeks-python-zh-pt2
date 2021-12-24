# PyQt5 QCalendarWidget–检查其是否有焦点

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendar widget-检查其是否有焦点/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-checking-if-its-has-focus-or-not/)

在本文中，我们将看到如何检查 QCalendarWidget 是否有焦点。焦点基本上是输入焦点，默认情况下它没有焦点，但是当应用程序执行时，鼠标点击它，它会获得焦点，但是当鼠标点击其他小部件时，它的焦点会转移。

> 为此，我们将对 QCalendarWidget 对象使用`hasFocus`方法。
> 
> **语法:** calendar.hasFocus()
> 
> **论证:**不需要论证
> 
> **返回:**返回 bool

**实施步骤:**
1。创建主窗口
2。创建日历部件
3。在不同的位置创建一个线编辑小部件
4。创建一个标签来显示焦点状态
5。每隔 200 毫秒创建一个调用动作的 QTimer 对象
6。在计时器操作中，检查日历焦点

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

        # checking edit focus
        value = self.calendar.hasFocus()

        # setting text to the label
        self.label.setText("Has Focus : " + str(value))

        # creating a timer object
        timer = QTimer(self)
        timer.timeout.connect(self.show_time)
        timer.start(200)

        # creating a line edit
        line = QLineEdit(self)

        # setting geometry tot he line edit
        line.setGeometry(500, 100, 100, 40)

    # method called by the timer
    def show_time(self):

        # checking focus
        value = str(self.calendar.hasFocus())

        # setting text through label
        self.label.setText("Has Focus : " + value)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-427426-1" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200609000724/Python-2020-06-08-23-48-53.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200609000724/Python-2020-06-08-23-48-53.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200609000724/Python-2020-06-08-23-48-53.mp4)</video>