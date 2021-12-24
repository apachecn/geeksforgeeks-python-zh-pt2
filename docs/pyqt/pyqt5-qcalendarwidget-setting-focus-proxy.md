# PyQt5 QCalendarWidget–设置焦点代理

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-setting-focus-proxy/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-focus-proxy/)

在本文中，我们将看到如何将焦点代理设置为 QCalendarWidget。焦点代理是间接将焦点设置到日历，即通过将焦点设置到它的子代。例如，一些小部件可以“有焦点”，但是创建一个子小部件，比如 QLineEdit，来实际处理焦点。在这种情况下，小部件可以将行编辑设置为其焦点代理。默认情况下，日历的 QTableView 有焦点代理。

> 为此，我们将对 QCalendarWidget 对象使用`setFocusProxy`方法。
> 
> **语法:** calendar.setFocusProxy(子)
> 
> **参数:**它以 QWidget 类型对象为参数
> 
> **返回:**不返回

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

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-426182-1" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200607024618/Python-2020-06-07-02-45-49.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200607024618/Python-2020-06-07-02-45-49.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200607024618/Python-2020-06-07-02-45-49.mp4)</video>