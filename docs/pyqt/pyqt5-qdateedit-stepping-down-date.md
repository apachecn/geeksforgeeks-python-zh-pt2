# pyqt 5 qdate edit–卸任日期

> 原文:[https://www . geesforgeks . org/pyqt 5-qdatedit-下台-日期/](https://www.geeksforgeeks.org/pyqt5-qdateedit-stepping-down-date/)

在这篇文章中，我们将看到我们如何减少，即增加日期编辑的日期。步进日期意味着减少日期，它减少当前选定的部分，即日、月或年。向下箭头按钮执行相同的操作，尽管我们可以移除该按钮并制作自己的按钮。

**注意:**当任一段达到最大值时，则不再递增，例如，月段在第 12 个月后不能递增

为了做到这一点，我们对 QDateEdit 对象使用`stepDown`方法

> **语法:** date.stepDown()
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
        push = QPushButton("Step Down", self)

        # setting geometry of the push button
        push.setGeometry(100, 170, 100, 30)

        # adding action to the push button when it get clicked
        push.clicked.connect(lambda: push_method())

        # method called by the push button
        def push_method():

            # stepping down
            date.stepDown()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-444114-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200702033052/Python-2020-07-02-03-30-20.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200702033052/Python-2020-07-02-03-30-20.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200702033052/Python-2020-07-02-03-30-20.mp4)</video>