# PYqt 5 QDateTimeedit–设置电流部分

> 原文:[https://www . geesforgeks . org/pyqt 5-qdatetime edit-setting-current-section/](https://www.geeksforgeeks.org/pyqt5-qdatetimeedit-setting-current-section/)

在本文中，我们将看到如何以编程方式设置 QDateTimeEdit 小部件中的当前部分。在 QDateTimeedit 小部件中有许多部分，如年、月、小时、分钟部分。用户可以在鼠标或键盘的帮助下选择任何部分，并对当前部分执行递增和递减操作。

为了做到这一点，我们将使用`setCurrentSection`方法和 QDateTimeEdit 对象。

> **语法:**datetimeedit . set current session(节)
> 
> **自变量:**以节对象为自变量
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

        # creating a push button
        push = QPushButton("Press", self)

        # setting geometry to the push button
        push.setGeometry(120, 160, 120, 35)

        # when push button get clicked connect to the method
        push.clicked.connect(lambda: push_method())

        def push_method():

            # set the current section
            datetimeedit.setCurrentSection(QDateTimeEdit.MonthSection)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-451427-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200712023342/Python-2020-07-12-02-33-14.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200712023342/Python-2020-07-12-02-33-14.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200712023342/Python-2020-07-12-02-33-14.mp4)</video>