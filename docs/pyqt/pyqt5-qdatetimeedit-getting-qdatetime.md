# PyQt5 QDateTimeEdit – Get QDateTime

> 哎哎哎:# t0]https://www . geeksforgeeks . org/pyqt 5-qdatetimeedit-getting-qdatetime/

在本文中，我们将看到如何获取 QDateTimeEdit 小部件的 QDateTime 对象。QDateTime 基本上是 QDate 和 QTime 的组合，即它既有日期又有时间。而 QDateTimeEdit 小部件用于显示或接收 QDateTime。我们可以借助`setDateTime`方法将 QDateTime 设置为它。

为了做到这一点，我们将使用`dateTime`方法和 QDateTimeEdit 对象。

> **语法 ：** datetimeedit.dateTime（）
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

        # creating a QDateTimeEdit widget
        datetimeedit = QDateTimeEdit(self)

        # setting geometry
        datetimeedit.setGeometry(100, 100, 150, 35)

        # QDateTime
        dt = QDateTime(2020, 10, 10, 21, 30)

        # setting date time to datetimeedit
        datetimeedit.setDateTime(dt)

        # creating a label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry to the label
        label.setGeometry(100, 160, 200, 60)

        # making label multi line
        label.setWordWrap(True)

        # getting current datetime
        value = datetimeedit.dateTime()

        # setting text to label
        label.setText("DateTime : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/98572c5de8822a722458d8445a1b3c93.png)