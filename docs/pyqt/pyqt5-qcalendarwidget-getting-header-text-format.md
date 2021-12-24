# PyQt5 QCalendarWidget–获取标题文本格式

> 原文:[https://www . geesforgeks . org/pyqt5-qcalendarwidget-get-header-text-format/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-getting-header-text-format/)

在本文中，我们将看到如何获得 QCalendarWidget 的标题的文本格式。日历有两个标题，一个显示星期几，即水平标题，另一个是显示星期几的垂直标题。我们可以借助`setHeaderTextFormat`方法将文本设置为页眉，设置页眉文本格式意味着将格式即样式设置为这两个页眉。

> 为此，我们将对 QCalendarWidget 对象使用`headerTextFormat`方法。
> 
> **语法:** calendar.headerTextFormat()
> 
> **论证:**不需要论证
> 
> **返回:**它返回 QTextCharFormat 对象

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
        self.setGeometry(100, 100, 650, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        # creating a QCalendarWidget object
        self.calendar = QCalendarWidget(self)

        # setting geometry to the calender
        self.calendar.setGeometry(50, 10, 400, 250)

        # setting cursor
        self.calendar.setCursor(Qt.PointingHandCursor)

        # format
        format = QTextCharFormat()
        format.setFont(QFont('Times', 12))

        # setting header text format
        self.calendar.setHeaderTextFormat(format)

        # creating label to show the properties
        self.label = QLabel(self)

        # setting geometry to the label
        self.label.setGeometry(100, 280, 250, 60)

        # making label multi line
        self.label.setWordWrap(True)

        # getting header text format
        value = self.calendar.headerTextFormat()

        # setting text to the label
        self.label.setText("Header Format : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/39d6e3b03095a93a73617678bcd51ce0.png)