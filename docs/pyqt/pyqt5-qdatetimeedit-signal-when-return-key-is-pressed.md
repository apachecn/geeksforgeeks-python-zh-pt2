# PYqt 5 QDateTiME edit–按下回车键时的信号

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdatetime edit-按回车键时发出信号/](https://www.geeksforgeeks.org/pyqt5-qdatetimeedit-signal-when-return-key-is-pressed/)

在本文中，我们将看到如何在 QDateTimeEdit 小部件上按下回车键时获得信号。QDateTime 基本上是 QDate 和 QTime 的组合，即它既有日期又有时间。而 QDateTimeEdit 小部件用于显示或接收 QDateTime。我们可以借助`setDateTime`方法将 QDateTime 设置为它。为了在按下回车键时获得信号，我们使用编辑完成信号，该信号在编辑完成时发出。当 QDateTime 失去焦点和按下回车键时，就会发生这种情况。

为了做到这一点，我们将使用`editingFinished`方法和 QDateTimeEdit 对象。

> **语法:**datetime edit . editing finished . connect(方法)
> 
> **自变量:**以方法为自变量
> 
> **返回:**返回无

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
        self.setGeometry(100, 100, 500, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        # creating a QDateTimeEdit widget
        datetimeedit = QDateTimeEdit(self)

        # setting geometry
        datetimeedit.setGeometry(100, 100, 150, 35)

        # setting date time to it
        datetimeedit.setDateTime(QDateTime(2020, 10, 10, 11, 30))

        # time
        time = QTime(21, 45)

        # setting only time
        datetimeedit.setTime(time)

        # creating a label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry to the label
        label.setGeometry(100, 160, 200, 60)

        # making label multi line
        label.setWordWrap(True)

        # getting editing finished signal
        datetimeedit.editingFinished.connect(lambda: label.setText("Editing Finished signal Emitted"))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-451339-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200711015923/Python-2020-07-11-01-58-59.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200711015923/Python-2020-07-11-01-58-59.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200711015923/Python-2020-07-11-01-58-59.mp4)</video>