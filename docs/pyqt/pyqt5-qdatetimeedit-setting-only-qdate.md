# PYqt 5 QDATetime edit–仅设置 QDate

> 原文:[https://www . geesforgeks . org/pyqt 5-qdatetime edit-setting-only-qdate/](https://www.geeksforgeeks.org/pyqt5-qdatetimeedit-setting-only-qdate/)

在本文中，我们将看到如何只将 QDate 设置为 QDateTimeEdit 小部件。QDateTime 基本上是 QDate 和 QTime 的组合，即它既有日期又有时间。而 QDateTimeEdit 小部件用于显示或接收 QDateTime。我们可以借助`setDateTime`方法将 QDateTime 设置为它。设置日期不会影响日期时间编辑的时间。

为了做到这一点，我们将使用`setDate`方法和 QDateTimeEdit 对象。

> **语法 ：** datetimeedit.setDate（date）
> 
> **自变量:**它以 QDate 对象为自变量
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

        # creating a QDateTimeEdit widget
        datetimeedit = QDateTimeEdit(self)

        # setting geometry
        datetimeedit.setGeometry(100, 100, 150, 35)

        # setting date time to it
        datetimeedit.setDateTime(QDateTime(2020, 10, 10, 11, 30))

        # date
        date = QDate(2020, 1, 1)

        # setting only date
        datetimeedit.setDate(date)

        # creating a label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry to the label
        label.setGeometry(100, 160, 200, 60)

        # making label multi line
        label.setWordWrap(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/473cc401819446df89fb4c83e4009769.png)