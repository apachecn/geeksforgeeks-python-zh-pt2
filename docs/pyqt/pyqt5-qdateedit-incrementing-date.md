# pyqt 5 qdateedit–递增日期

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdate edit-递增-date/](https://www.geeksforgeeks.org/pyqt5-qdateedit-incrementing-date/)

在这篇文章中，我们将看到我们如何增加，即提高日期编辑的日期。步进更新意味着增加日期，它增加当前选定的部分，即日、月或年。向上箭头按钮执行相同的操作，尽管我们可以移除该按钮并制作自己的按钮。

为了做到这一点，我们对 QDateEdit 对象使用`stepUp`方法

> **语法:** date.stepUp()
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

        # removing buttons
        date.setButtonSymbols(2)

        # setting geometry of the date edit
        date.setGeometry(100, 100, 150, 40)

        # creating a label
        push = QPushButton("Step Up", self)

        # setting geometry of the push button
        push.setGeometry(100, 170, 100, 30)

        # adding action to the push button when it get clicked
        push.clicked.connect(lambda: push_method())

        # method called by the push button
        def push_method():

            # steping up the date
            date.stepUp()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-444112-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200702032742/Python-2020-07-02-03-27-14.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200702032742/Python-2020-07-02-03-27-14.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200702032742/Python-2020-07-02-03-27-14.mp4)</video>