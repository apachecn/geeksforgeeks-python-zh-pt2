# PyQt5 QCalendarWidget–将皮肤设置为工具按钮

> 原文:[https://www . geeksforgeeks . org/pyqt5-qcalendarwidget-设置-皮肤到工具-按钮/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-skin-to-the-tool-buttons/)

在本文中，我们将看到如何为 QCalendarWidget 的工具按钮设置皮肤。工具按钮是顶部可用的按钮，即进入左侧和右侧页面的按钮，将皮肤设置为 QCalendarWidget 不同于将皮肤设置为其他小部件，日历是具有多个子组件的小部件，即我们也可以将皮肤设置为独立组件。皮肤基本上是背景图像，它根据地方的大小来调整大小

为此，我们将对 QCalendarWidget 对象使用 set 样式表方法，下面是样式表代码

```py
QCalendarWidget QToolButton
{
border-image : url(image.png);
}

```

下面是实现

```py
# importing libraries
from PyQt5.QtWidgets import * 
from PyQt5 import QtCore, QtGui
from PyQt5.QtGui import * 
from PyQt5.QtCore import * 
import sys

# QCalendarWidget Class
class Calendar(QCalendarWidget):

    # constructor
    def __init__(self, parent = None):
        super(Calendar, self).__init__(parent)

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
        # creating a QCalendarWidget object
        # as Calendar class inherits QCalendarWidget
        self.calendar = Calendar(self)

        # setting cursor
        self.calendar.setCursor(Qt.PointingHandCursor)

        # setting size of the calendar
        self.calendar.resize(350, 240)

        # move the calendar
        self.calendar.move(10, 10)

        # setting stylesheet
        # adding skin to the tool button
        self.calendar.setStyleSheet("QCalendarWidget QToolButton"
                                    "{"
                                    "background-image : url(image.png);"
                                    "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-438242-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200624025430/Python-2020-06-24-02-54-02.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200624025430/Python-2020-06-24-02-54-02.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200624025430/Python-2020-06-24-02-54-02.mp4)</video>