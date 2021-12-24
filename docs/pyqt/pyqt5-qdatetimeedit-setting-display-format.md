# PYqt5 QDateTimeedit–设置显示格式

> 原文:[https://www . geesforgeks . org/pyqt 5-qdatetime edit-setting-display-format/](https://www.geeksforgeeks.org/pyqt5-qdatetimeedit-setting-display-format/)

在本文中，我们将看到如何将日期的显示格式设置为 QDateTimeEdit。显示格式属性保存用于显示日期时间编辑的时间/日期的格式。默认情况下，我们看到的日期格式类似于 01-01-2000，尽管通过设置显示格式，我们可以将此日期设为 2020 年 1 月 1 日。

为了做到这一点，我们将使用`setDisplayFormat`方法和 QDateTimeEdit 对象。

> **语法:**datetimeedit . setdisplay format(格式)
> 
> **自变量:**以字符串为自变量
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

        # setting date format
        datetimeedit.setDisplayFormat("dd MMM yyyy")

        # creating a label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 80)

        # making label multi line
        label.setWordWrap(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-451436-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200713000543/Python-2020-07-13-00-05-17.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200713000543/Python-2020-07-13-00-05-17.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200713000543/Python-2020-07-13-00-05-17.mp4)</video>