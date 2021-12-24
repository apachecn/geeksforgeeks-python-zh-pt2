# PYqt5 QDateTiME 编辑–获取章节文本

> 原文:[https://www . geesforgeks . org/pyqt 5-qdatetime edit-get-section-text/](https://www.geeksforgeeks.org/pyqt5-qdatetimeedit-getting-section-text/)

在本文中，我们将看到如何获取 QDateTimeEdit 小部件的部分文本。在 QDateTimeedit 小部件中有许多部分，如年、月、小时、分钟部分。用户可以在鼠标或键盘的帮助下选择任何部分，并对所选部分执行递增和递减操作。部分文本用于仅获取选定部分的文本。

为了做到这一点，我们将使用`sectionText`方法和 QDateTimeEdit 对象。

> **语法 ：** 日期时间编辑.sectionText（section）
> 
> **自变量:**以节对象为自变量
> 
> **返回:**返回字符串

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

        # creating a label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry to the label
        label.setGeometry(100, 200, 200, 60)

        # making label multi line
        label.setWordWrap(True)

        # getting section at index 1
        section = datetimeedit.sectionAt(1)

        # getting section count
        value = datetimeedit.sectionText(section)

        # setting text to the label
        label.setText("Section Text: " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/2f74d23c9524014b41db68884429c137.png)