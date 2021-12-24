# PyQt5 QCalendarWidget–设置选择模式

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-设置-选择-模式/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-selection-mode/)

在本文中，我们将看到如何将选择模式设置为 QCalendarWidget。选择模式基本上是日历的质量如何选择日期。QCalendarWidget 有两种模式，第一种是 NoSelection 模式，其值为 0，在这种模式下，无法选择日期。另一个是 SingleSelection，它是默认模式，它的值是 1，在这个模式下一次可以选择一个日期。

> 为此，我们将对 QCalendarWidget 对象使用 setSelectionMode 方法。
> **语法:** calendar.setSelectionMode(模式)
> **参数:**取选择模式对象
> **返回:**不返回

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

        # setting selection mode
        calendar.setSelectionMode(QCalendarWidget.NoSelection)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-421596-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200530011853/Python-2020-05-30-01-18-22.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200530011853/Python-2020-05-30-01-18-22.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200530011853/Python-2020-05-30-01-18-22.mp4)</video>