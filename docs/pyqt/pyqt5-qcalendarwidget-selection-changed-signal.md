# PyQt5 QCalendarWidget–选择改变信号

> 原文:[https://www . geesforgeks . org/pyqt 5-qcalendarwidget-selection-changed-signal/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-selection-changed-signal/)

在本文中，我们将看到如何从 QCalendarWidget 获取选择更改信号。当前选择的日期改变时，会发出选择改变信号。用户可以使用鼠标或键盘更改当前选定的日期。

> 为此，我们将对 QCalendarWidget 对象使用 selectionChanged 方法。
> **语法:**calendar . selectionchanged . connect(lambda:print(“Selection Changed”))
> **引数:**它以方法为引数
> **执行的动作:**只要发出激活信号，它就会打印消息

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
        text = "Selection Changed signal (No.) : "

        # current count
        self.count = 0

        # getting the selection change signal and
        # when receives the signal printing the message
        calendar.selectionChanged.connect(lambda: label.setText(text + str(get_count())))

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

<video class="wp-video-shortcode" id="video-421785-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200601015035/Python-2020-06-01-01-50-06.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200601015035/Python-2020-06-01-01-50-06.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200601015035/Python-2020-06-01-01-50-06.mp4)</video>