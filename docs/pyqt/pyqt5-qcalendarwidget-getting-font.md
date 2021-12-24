# pyqt 5 qcalendarvdget–正在发行字体

> 哎哎哎:# t0]https://www . geeksforgeeks . org/pyqt 5-qcalendarvdget-getting-font/

在本文中，我们将看到如何获得 QCalendarWidget 的字体。字体是字体的特定大小、重量和样式。每种字体都是一组匹配的字体，每个字形一个。通过改变字体，我们可以改变日历中文本的样式。我们可以使用`setFont`方法更改/设置字体。

> 为此，我们将对 QCalendarWidget 对象使用`font`方法。
> 
> **语法:** calendar.font()
> 
> **论证:**不需要论证
> 
> **返回:**返回 QFont 对象

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
        self.calender = QCalendarWidget(self)

        # setting geometry to the calender
        self.calender.setGeometry(50, 10, 400, 250)

        # setting cursor
        self.calender.setCursor(Qt.PointingHandCursor)

        # font
        font = QFont('Times', 5)

        # setting font to the calendar
        self.calender.setFont(font)

        # creating label to show the properties
        self.label = QLabel(self)

        # setting geometry to the label
        self.label.setGeometry(100, 280, 250, 60)

        # making label multi line
        self.label.setWordWrap(True)

        # getting font
        value = self.calender.font()

        # setting text to the label
        self.label.setText("Font : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/0d4005bfa79f789a4c368c2c336fadc1.png)