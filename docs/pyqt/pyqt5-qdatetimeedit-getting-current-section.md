# pyqt 5 qdatetime 编辑–获取当前部分

> 原文:[https://www . geesforgeks . org/pyqt 5-qdatetime edit-get-current-section/](https://www.geeksforgeeks.org/pyqt5-qdatetimeedit-getting-current-section/)

在本文中，我们将看到如何获取 QDateTimeEdit 小部件的当前部分。在 QDateTimeedit 小部件中有许多部分，如年、月、小时、分钟部分。用户可以在鼠标或键盘的帮助下选择任何部分，并对当前部分执行递增和递减操作。我们可以借助`setCurrentSection`方法编程设置当前节。

为了做到这一点，我们将使用`currentSection`方法和 QDateTimeEdit 对象。

> **语法:** datetimeedit.currentSection()
> 
> **论证:**不需要论证
> 
> **返回:**它返回截面对象，但打印时会显示与之相关的值

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

        # getting current section
        value = datetimeedit.currentSection()

        # setting text to the label
        label.setText("Section : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/95ed768b4f86e0ea362af856f5144768.png)