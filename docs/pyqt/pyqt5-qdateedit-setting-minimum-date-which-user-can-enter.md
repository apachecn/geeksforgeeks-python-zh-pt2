# PyQt5 qdate edit–设置用户可以输入的最小日期

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdate edit-setting-最小日期-用户可以输入的日期/](https://www.geeksforgeeks.org/pyqt5-qdateedit-setting-minimum-date-which-user-can-enter/)

在本文中，我们将看到如何将最小日期设置为 QDateEdit。有时需要设置最小日期，这样用户就不能输入超出最小日期日期。例如，当要求用户输入酒店预订日期时，不允许用户输入过去的日期，这时就需要设置最小日期。

为了做到这一点，我们对 QDateEdit 对象使用`setMinimumDate`方法

> **语法:** date.setMinimumDate(日期)
> 
> **参数:**取 QDate 对象参数
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
        d = QDate(2020, 1, 1)

        # setting minimum date
        date.setMinimumDate(d)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-445963-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200704020538/Python-2020-07-04-02-05-14.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200704020538/Python-2020-07-04-02-05-14.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200704020538/Python-2020-07-04-02-05-14.mp4)</video>