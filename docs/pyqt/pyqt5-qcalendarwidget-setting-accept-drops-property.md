# PyQt5 QcalendarWidget–设置接受滴属性

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-setting-accept-drops-property/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-accept-drops-property/)

在本文中，我们将看到如何设置 QCalendarWidget 的 accept drop 属性。我们知道我们可以使用带有日历对象的 setDragEnabled 方法来启用拖动，但是拖动文本有什么用，我们不能把它放在任何地方。允许接受删除意味着日历现在有一个属性来接受其他日历小部件的删除文本。接受滴用于设置年份，因为它是作为子对象的旋转框对象。

> 为此，我们将对 QCalendarWidget 对象使用 setAcceptDrops 方法。
> **语法:**calendar . set accept drops(True)
> **参数:**它以 bool 为参数
> **执行的动作:**它返回 None

下面是实现

## 蟒蛇 3

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

        # accepting drops
        calendar.setAcceptDrops(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-423387-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200603010456/Python-2020-06-03-01-04-05.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200603010456/Python-2020-06-03-01-04-05.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200603010456/Python-2020-06-03-01-04-05.mp4)</video>