# PyQt5 qdate edit–设置用户可以输入的日期范围

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdate edit-setting-date-range-哪些用户可以输入/](https://www.geeksforgeeks.org/pyqt5-qdateedit-setting-date-range-which-user-can-enter/)

在本文中，我们将看到如何将日期范围设置为 QDateEdit。日期范围意味着用户只能输入设置范围内的日期。有时需要设置日期范围，例如当用户被要求在 10 天内选择会议日期时，则需要设置范围。单独我们可以分别借助`setMinimumDate`和`setMaximumDate`方法设置最小和最大日期。

为了做到这一点，我们对 QDateEdit 对象使用`setDateRange`方法

> **语法:**日期.设置日期范围(最小值，最大值)
> 
> **自变量:**取两个 QDate 对象作为自变量自变量
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
        d1 = QDate(2020, 10, 10)
        d2 = QDate(2020, 10, 20)

        # setting date range
        date.setDateRange(d1, d2)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-445968-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200704023827/Python-2020-07-04-02-38-00.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200704023827/Python-2020-07-04-02-38-00.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200704023827/Python-2020-07-04-02-38-00.mp4)</video>