# PyQt5 qdate edit–获取可设置的最小日期时间

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdate edit-get-最小日期-时间-可以设置的时间/](https://www.geeksforgeeks.org/pyqt5-qdateedit-getting-minimum-date-time-which-can-be-set/)

在本文中，我们将看到如何获得 QDateEdit 的最小日期时间。有时需要设置最小日期时间，以便用户不能输入超出最小日期时间的日期时间。我们可以借助`setDateTime`方法将日期时间设置为日期编辑。借助`setMinimumDateTime`方法，可以将最小日期时间设置为日期编辑。

为了做到这一点，我们对 QDateEdit 对象使用`minimumDateTime`方法

> **语法:**date . minimumatetime()
> 
> **论证:**不需要论证
> 
> **返回:**返回 QDateTime 对象

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
        d = QDateTime(2020, 1, 1, 10, 30)

        # setting minimum date time
        date.setMinimumDateTime(d)

        # creating a label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry
        label.setGeometry(100, 150, 200, 60)

        # making label multiline
        label.setWordWrap(True)

        # getting minimum date time
        value = date.minimumDateTime()

        # setting text to the label
        label.setText("Min Date Time : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/844ec413e13597416f50c15ea48e8523.png)