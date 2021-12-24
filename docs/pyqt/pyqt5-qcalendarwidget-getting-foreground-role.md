# PyQt5 QCalendarWidget–获取前台角色

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-get-前台-角色/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-getting-foreground-role/)

在本文中，我们将看到如何获得 QCalendarWidget 的前台角色。日历中基本上有两种角色，一种是前台，一种是后台。前景角色定义日历调色板中用于绘制前景的颜色。如果未设置明确的前台角色，前台将返回一个与后台角色形成对比的角色。我们可以借助 setForegroundRole 方法设置前台角色。

> 为此，我们将对 QCalendarWidget 对象使用 foregroundRole 方法。
> **语法:**calendar . foregroundrole()
> **参数:**不需要参数
> **返回:**返回 QPalette。ColorRole 对象，但打印时显示与角色相关的值

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
        self.setGeometry(100, 100, 650, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):
        # creating a QCalendarWidget object
        self.calender = QCalendarWidget(self)

        # setting geometry to the calendar
        self.calender.setGeometry(50, 10, 400, 250)

        # setting cursor
        self.calender.setCursor(Qt.PointingHandCursor)

        # setting foreround role
        self.calender.setForegroundRole(QPalette.Base)

        # getting palette and setting color to the background to it
        p = self.calender.palette()
        p.setColor(self.calender.foregroundRole(), Qt.darkGray)
        self.calender.setPalette(p)

        # creating label to show the properties
        self.label = QLabel(self)

        # setting geometry to the label
        self.label.setGeometry(100, 280, 250, 60)

        # making label multi line
        self.label.setWordWrap(True)

        # getting foreground role
        value = self.calender.foregroundRole()

        # setting text to the label
        self.label.setText("Fore ground role : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/633668c69438d5f09060436ad914eba0.png)