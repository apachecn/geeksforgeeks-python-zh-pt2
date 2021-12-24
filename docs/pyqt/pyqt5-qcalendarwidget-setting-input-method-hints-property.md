# PyQt5 QCalendarWidget–设置输入法提示属性

> 原文:[https://www . geesforgeks . org/pyqt5-qcalendarwidget-设置-输入法-提示-属性/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-input-method-hints-property/)

在本文中，我们将看到如何将输入法属性设置为 QCalendarWidget。输入法提示由输入法用来检索关于输入法应该如何操作的提示。例如，如果 Qt。ImhFormattedNumbersOnly 如果设置了一个标志，输入法可能会更改其视觉组件，以反映日历小部件中只能输入数字。

> 为此，我们将对 QCalendarWidget 对象使用`setInputMethodHints`方法。
> 
> **语法:**行事历。setinversiontimehints(Qt)。imhpreferlatin)
> 
> **自变量:**以方法提示对象为自变量
> 
> **返回:**不返回

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

        # setting input method hint
        self.calendar.setInputMethodHints(Qt.ImhPreferNumbers)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-428650-1" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200610180231/Python-2020-06-10-18-01-54.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200610180231/Python-2020-06-10-18-01-54.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200610180231/Python-2020-06-10-18-01-54.mp4)</video>