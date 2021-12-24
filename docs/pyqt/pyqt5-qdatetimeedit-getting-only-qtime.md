# pyqt 5 qdatetime 编辑–仅获取 Qt time

> 原文:[https://www . geesforgeks . org/pyqt5-qdatetime edit-get-only-qtime/](https://www.geeksforgeeks.org/pyqt5-qdatetimeedit-getting-only-qtime/)

在本文中，我们将看到如何只获取 QDateTimeEdit 小部件的 QTime。QDateTime 基本上是 QDate 和 QTime 的组合，即它既有日期又有时间。而 QDateTimeEdit 小部件用于显示或接收 QDateTime。我们可以借助`setDateTime`方法将 QDateTime 设置为它。设置时间不会影响 QDateTimeEdit 的日期，可以借助`setTime`方法进行设置。

为了做到这一点，我们将使用`time`方法和 QDateTimeEdit 对象。

> **语法 ：** 日期时间编辑时间（）
> 
> **论证:**不需要论证
> 
> **返回:**返回 QTime 对象

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

        # getting current time
        value = datetimeedit.time()

        # setting text to the label
        label.setText("Time : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/58226d74b0941af01045fe6fc0279c3c.png)