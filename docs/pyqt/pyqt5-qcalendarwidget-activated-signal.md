# PyQt5 QCalendarWidget–激活信号

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-activated-signal/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-activated-signal/)

在本文中，我们将看到如何从 QCalendarWidget 获取激活的信号。每当用户按下回车键或回车键或双击日历小部件中的日期时，都会发出激活信号。

> 为此，我们将对 QCalendarWidget 对象使用 actiavted 方法。
> **语法:**Calendar . activated . connect(lambda:print(“Calendar get activated”))
> **自变量:**它以方法为自变量
> **执行的动作:**每当发出激活信号时它就会打印消息

下面是实现

## 蟒蛇 3

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
        self.setGeometry(100, 100, 600, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        # creating a QCalendarWidget object
        calendar = QCalendarWidget(self)

        # setting geometry to the calendar
        calendar.setGeometry(10, 10, 400, 250)

        # creating a label
        label = QLabel(self)

        # setting geometry to the label
        label.setGeometry(100, 280, 250, 60)

        # making label multi line
        label.setWordWrap(True)

        # text
        text = "Activated Signals received (No.) : "

        # current count
        self.count = 0

        # getting the activated signal and
        # when receives the signal printing the message
        calendar.activated.connect(lambda: label.setText(text + str(get_count())))

        # method to increase the count value
        def get_count():
            self.count += 1
            return self.count

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-421586-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200531005716/Python-2020-05-31-00-56-24.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200531005716/Python-2020-05-31-00-56-24.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200531005716/Python-2020-05-31-00-56-24.mp4)</video>