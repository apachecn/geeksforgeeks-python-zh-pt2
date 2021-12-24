# pyqt 5 qdate edit–设置可设置的最短时间

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdate edit-setting-最小可设置时间/](https://www.geeksforgeeks.org/pyqt5-qdateedit-setting-minimum-time-which-can-be-set/)

在本文中，我们将了解如何将最短时间设置为 QDateEdit。有时需要设置最短时间，这样用户就不能输入/存储超过最短时间的时间。我们可以借助`setTime`方法将时间设置为日期编辑。

为了做到这一点，我们对 QDateEdit 对象使用`setMinimumTime`方法

> **语法:**date . setminimummtime(时间)
> 
> **自变量:**它以 QTime 对象为自变量
> 
> **返回:**返回

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

        # QTime object
        t = QTime(10, 30)

        # setting minimum time
        date.setMinimumTime(t)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/50909d7819ceacb6babae3836f54dc8a.png)