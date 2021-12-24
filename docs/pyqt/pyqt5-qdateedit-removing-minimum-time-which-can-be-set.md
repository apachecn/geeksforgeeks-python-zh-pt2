# PYqt 5 QDateedit–删除可设置的最短时间

> 原文:[https://www . geesforgeks . org/pyqt 5-qdatedit-remove-最小可设置时间/](https://www.geeksforgeeks.org/pyqt5-qdateedit-removing-minimum-time-which-can-be-set/)

在本文中，我们将了解如何删除 QDateEdit 的最短时间。有时需要设置最短时间，这样用户就不能输入/存储超过最短时间的时间。我们可以借助`setTime`方法将时间设置为日期编辑。借助`setMinimumTime`方法，可以将最短时间设置为日期编辑。

为了做到这一点，我们对 QDateEdit 对象使用`clearMinimumTime`方法

> **语法:**date . clearminimummtime()
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

        # QTime object
        t = QTime(10, 30)

        # setting minimum time
        date.setMinimumTime(t)

        # removing minimum time
        date.clearMinimumTime()

        # creating a label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry
        label.setGeometry(100, 150, 200, 60)

        # making label multiline
        label.setWordWrap(True)

        # getting minimum time
        value = date.minimumTime()

        # setting text to the label
        label.setText("Min Time : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/963a2eceb65b051c9030edfc682451bb.png)