# PyQt5 QCalendarWidget–获取焦点代理

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-get-focus-proxy/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-getting-focus-proxy/)

在本文中，我们将看到如何获得 QCalendarWidget 的焦点代理。焦点代理是间接将焦点设置到日历，即通过将焦点设置到它的子代。例如，一些小部件可以“有焦点”，但是创建一个子小部件，比如 QLineEdit，来实际处理焦点。在这种情况下，小部件可以将行编辑设置为其焦点代理。默认情况下，日历的 QTableView 有焦点代理，尽管可以借助`setFocusProxy`方法进行更改。

> 为此，我们将对 QCalendarWidget 对象使用`focusProxy`方法。
> 
> **语法:** calendar.focusProxy()
> 
> **论证:**不需要论证
> 
> **返回:**返回 QWidget 对象

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

        # getting child
        child = self.calender.children()[3]

        # setting focus proxy
        self.calender.setFocusProxy(child)

        # creating label to show the properties
        self.label = QLabel(self)

        # setting geometry to the label
        self.label.setGeometry(100, 280, 250, 60)

        # making label multi line
        self.label.setWordWrap(True)

        # getting focus proxy
        value = self.calender.focusProxy()

        # setting text to the label
        self.label.setText("Focus Proxy  : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/f2f46570e7091f6ba9f31cca91d04d82.png)