# PyQt5 QCalendarWidget–释放抓取的键盘输入

> 原文:[https://www . geesforgeks . org/pyqt5-qcalendarwidget-release-抓取-键盘-输入/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-releasing-grabbed-keyboard-input/)

在本文中，我们将看到如何取消绑定，即释放 QCalendarWidget 的键盘输入。通过抓取键盘，日历不会受到影响，只是它不会接收任何键盘事件。`setFocus`照常移动焦点，但新的焦点小部件只有在调用`releaseKeyboard`后才接收键盘事件。抓取可以借助`grabKeyboard`方法完成。

> 为此，我们将对 QCalendarWidget 对象使用`releaseKeyboard`方法。
> 
> **语法:** calendar.releaseKeyboard()
> 
> **论证:**不需要论证
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
        self.calendar = QCalendarWidget(self)

        # setting geometry to the calender
        self.calendar.setGeometry(50, 10, 400, 250)

        # setting cursor
        self.calendar.setCursor(Qt.PointingHandCursor)

        # grabbing keyboard input
        self.calendar.grabKeyboard()

        # creating a push button
        push = QPushButton("Release Keyboard", self)

        # setting geometry tot he push button
        push.setGeometry(100, 280, 150, 40)

        # adding action to the push button
        push.clicked.connect(self.do_action)

    def do_action(self):

        # releasing the keyboard
        self.calendar.releaseKeyboard()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
最初键盘输入不工作，但当释放方法调用它时开始工作

<video class="wp-video-shortcode" id="video-426224-1" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200608040900/Python-2020-06-08-04-08-32.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200608040900/Python-2020-06-08-04-08-32.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200608040900/Python-2020-06-08-04-08-32.mp4)</video>