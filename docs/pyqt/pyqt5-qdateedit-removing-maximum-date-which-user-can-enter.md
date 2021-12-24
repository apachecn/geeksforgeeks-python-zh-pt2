# PyQt5 qdate edit–删除用户可以输入的最大日期

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdate edit-remove-最大日期-用户可以输入的日期/](https://www.geeksforgeeks.org/pyqt5-qdateedit-removing-maximum-date-which-user-can-enter/)

在本文中，我们将看到如何删除 QDateEdit 的最大日期。有时需要设置最大日期，这样用户就不能输入超过最大日期的日期。例如，当用户被要求输入出生日期时，不允许用户输入将来的日期，这时就需要设置最大日期。借助`setMaximumDate`方法可以设置最大日期。

为了做到这一点，我们对 QDateEdit 对象使用`clearMaximumDate`方法

> **语法:** date.clearMaximumDate()
> 
> **论证:**不需要论证
> 
> **返回:**返回无

下面是实现

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
        d = QDate(2020, 1, 1)

        # setting maximum date
        date.setMaximumDate(d)

        # removing max date
        date.clearMaximumDate()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-445906-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200704015418/Python-2020-07-04-01-53-55.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200704015418/Python-2020-07-04-01-53-55.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200704015418/Python-2020-07-04-01-53-55.mp4)</video>