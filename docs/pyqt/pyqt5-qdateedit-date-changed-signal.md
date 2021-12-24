# pyqt 5 qdateedit–date changed signal

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdate edit-date-changed-signal/](https://www.geeksforgeeks.org/pyqt5-qdateedit-date-changed-signal/)

在本文中，我们将了解如何获取 QDateEdit 的日期更改信号。日期更改信号在日期编辑的日期更改时出现，用户可以通过光标或键盘更改日期，也可以通过`setDate`方法编程设置日期。

为了做到这一点，我们对 QDateEdit 对象使用`dateChanged`方法

> **语法:** date.dateChanged.connect(方法)
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

        # creating a QDateEdit widget
        date = QDateEdit(self)

        # setting geometry of the date edit
        date.setGeometry(100, 100, 150, 40)

        # creating a label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry
        label.setGeometry(100, 150, 200, 60)

        # making label multiline
        label.setWordWrap(True)

        # date  change signal
        date.dateChanged.connect(lambda: method())

        # method called when signal emitted
        def method():

            # setting text to the label
            label.setText("Date  Changed Signal")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-445884-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200703030231/Python-2020-07-03-03-02-14.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200703030231/Python-2020-07-03-03-02-14.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200703030231/Python-2020-07-03-03-02-14.mp4)</video>