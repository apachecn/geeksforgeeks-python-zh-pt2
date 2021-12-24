# PYqt 5 QDateedit–时变信号

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdate edit-time-changed-signal/](https://www.geeksforgeeks.org/pyqt5-qdateedit-time-changed-signal/)

在本文中，我们将了解如何获取 QDateEdit 的时间变化信号。与普通的类似日期不同，我们可以借助`setDateTime`方法为其设置日期时间。但是借助`setTime`方法，我们也可以只设置时间而不改变日期。每当日期编辑时间改变时，就会发出此信号。

为了做到这一点，我们对 QDateEdit 对象使用`timeChanged`方法

> **语法:** date.timeChanged.connect(方法)
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

        # time change signal
        date.timeChanged.connect(lambda: method())

        # method called when signal emitted
        def method():

            # setting text to the label
            label.setText("Time Changed Signal")

        # date time
        time = QTime(11, 20, 0)

        # setting time
        date.setTime(time)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/a81943a761a2727ff4bf3d6135c49f16.png)