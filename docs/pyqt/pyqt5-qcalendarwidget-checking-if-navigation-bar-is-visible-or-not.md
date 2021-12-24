# PyQt5 QCalendarWidget–检查导航栏是否可见

> 原文:[https://www . geeksforgeeks . org/pyqt5-qcalendarwidget-checking-navigation-bar-visible-or-not/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-checking-if-navigation-bar-is-visible-or-not/)

在本文中，我们将看到如何检查 QCalendarWidget 的导航栏是否可见。导航栏是日历的顶部，用于更改下个月、上个月、月份选择、年份选择。默认情况下，导航栏是可见的，尽管我们可以在 setNavigationBarVisible 方法的帮助下随时隐藏它，下面是 QCalendarWidget 的导航栏表示。

![](img/25d66a5c0d26a276abc3b4ca1b0af24e.png)

> 为此，我们将对 QCalendarWidget 对象使用 isNavigationBarVisible 方法。
> **语法:**calendar . isnavigationbarvisible()
> **参数:**不需要参数
> **返回:**返回 bool

下面是实现

## 蟒蛇 3

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
        self.setGeometry(100, 100, 600, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        # creating a QCalendarWidget object
        calendar = QCalendarWidget(self)

        # setting geometry to the calendar
        calendar.setGeometry(10, 10, 400, 250)

        # hiding the navigation bar
        calendar.setNavigationBarVisible(False)

        # creating label
        label = QLabel(self)

        # setting geometry to the label
        label.setGeometry(100, 270, 250, 60)

        # making label multi line
        label.setWordWrap(True)

        # checking if the navigation bar is visible
        check = calendar.isNavigationBarVisible()

        # setting text to the label
        label.setText("Navigation Bar Visible : " + str(check))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/83b121546ae1b5bc6b40dee917649419.png)