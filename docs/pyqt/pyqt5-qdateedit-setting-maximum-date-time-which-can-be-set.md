# PyQt5 qdate edit–设置可设置的最大日期时间

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdate edit-设置-最大日期-时间-可以设置的时间/](https://www.geeksforgeeks.org/pyqt5-qdateedit-setting-maximum-date-time-which-can-be-set/)

在本文中，我们将看到如何将最大日期时间设置为 QDateEdit。有时需要设置最大日期时间，以便用户不能输入超过最大日期时间日期时间。我们可以借助`setDateTime`方法将日期时间设置为日期编辑。

为了做到这一点，我们对 QDateEdit 对象使用`setMaximumDateTime`方法

> **语法:**date . setmaximumdatetime(date _ time)
> 
> **参数:**它以 QDateTime 对象为参数
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

        # creating a QDateEdit widget
        date = QDateEdit(self)

        # setting geometry of the date edit
        date.setGeometry(100, 100, 200, 40)

        # alignment
        a_flag = Qt.AlignCenter

        # setting alignment of date
        date.setAlignment(a_flag)

        # QDate object
        d = QDateTime(2020, 1, 1, 10, 30)

        # setting maximum date time
        date.setMaximumDateTime(d)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-445969-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200704030707/Python-2020-07-04-03-06-46.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200704030707/Python-2020-07-04-03-06-46.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200704030707/Python-2020-07-04-03-06-46.mp4)</video>