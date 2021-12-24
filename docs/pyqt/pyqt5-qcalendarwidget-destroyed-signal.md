# PyQt5 QCalendarWidget–破坏信号

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-销毁-signal/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-destroyed-signal/)

在本文中，我们将看到如何从 QCalendarWidget 获取被破坏的信号。在 QCalendarWidget 被销毁之前，在 QPointer 的任何实例被通知之后，立即发出销毁信号，并且不能被阻止。发出此信号后，所有对象的子对象都会立即被销毁。

> 为此，我们将对 QCalendarWidget 对象使用销毁方法。
> **语法:**calendar . designed . connect(lambda:print(“销毁信号”))
> **参数:**它以方法作为参数
> **执行的动作:**每当发出激活的信号时它就会打印消息

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
        calendar.setGeometry(50, 50, 400, 250)

        # creating a label
        label = QLabel(self)

        # setting geometry to the label
        label.setGeometry(100, 280, 250, 60)

        # making label multi line
        label.setWordWrap(True)

        # text
        text = "Destroyed Signal Emitted "

        # getting the destroyed signal and
        # when receives the signal printing the message
        calendar.destroyed.connect(lambda: label.setText(text))

        # creating push button
        push = QPushButton("Destroy ", self)

        # adding action to it
        push.clicked.connect(lambda: calendar.deleteLater())

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-421775-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200531020844/Python-2020-05-31-02-08-20.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200531020844/Python-2020-05-31-02-08-20.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200531020844/Python-2020-05-31-02-08-20.mp4)</video>