# 第 5 个日历编辑–选择整个日期

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdate edit-select-全日空/](https://www.geeksforgeeks.org/pyqt5-qdateedit-selecting-whole-date/)

在本文中，我们将看到如何选择 QDateEdit 的整个日期。用户可以在光标和键盘的帮助下为日期编辑设置日期。选择日期意味着日期文本，选择日期用于复制或覆盖日期编辑文本。

为了做到这一点，我们对 QDateEdit 对象使用`selectAll`方法

> **语法:**日期。选择所有()
> 
> **论证:**不需要论证
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
        date.setGeometry(100, 100, 150, 40)

        # creating push button
        push = QPushButton("Select", self)

        # setting geometry to the push button
        push.setGeometry(100, 150, 120, 30)

        # adding action to the push button
        # when it get clicked
        push.clicked.connect(lambda: push_method())

        # method called by push button
        def push_method():

            # selecting text
            date.selectAll()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-445870-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200703013936/Python-2020-07-03-01-39-00.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200703013936/Python-2020-07-03-01-39-00.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200703013936/Python-2020-07-03-01-39-00.mp4)</video>