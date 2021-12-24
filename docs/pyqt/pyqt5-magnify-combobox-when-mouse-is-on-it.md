# PyQt5–鼠标在组合框上时放大组合框

> 原文:[https://www . geeksforgeeks . org/pyqt 5-放大-组合框-鼠标在上面时/](https://www.geeksforgeeks.org/pyqt5-magnify-combobox-when-mouse-is-on-it/)

在本文中，我们将看到当鼠标在组合框上时，我们如何放大它。放大是指当光标在组合框上时，放大组合框的大小。我们不能使用样式表改变组合框的大小，因此我们不能在样式表中使用悬停。为了知道鼠标何时在组合框上，我们使用`underMouse`方法

为了做到这一点，我们使用`underMouse`方法。

> **语法:**组合框.鼠标下()
> 
> **论证:**不需要论证
> 
> **返回:**返回 bool

**实施步骤:**
1。创建一个组合框。
2。创建一个定时器对象，每隔 100 毫秒调用一个函数。
3。在计时器功能中，检查组合框是否在鼠标下方。
4。如果组合框在鼠标下面，增加它的大小，否则使它的大小变小。

以下是实施–

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

    # method for widgets
    def UiComponents(self):
        # creating a check-able combo box object
        self.combo_box = QComboBox(self)

        # setting geometry of combo box
        self.combo_box.setGeometry(200, 150, 100, 30)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # setting stylesheet of the combo box
        self.combo_box.setStyleSheet("border : 1px solid red;")

        # creating a timer object
        timer = QTimer(self)

        # adding action to the timer
        timer.timeout.connect(self.do_something)

        # starting timer
        timer.start(100)

    # action called by the timer
    def do_something(self):

        # checking is mouse is on combo box
        if self.combo_box.underMouse():
            # making size larger
            self.combo_box.resize(110, 40)

        else:
            # making size smaller
            self.combo_box.resize(100, 30)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-408442-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200506002734/Python-06-05-2020-00_23_18.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200506002734/Python-06-05-2020-00_23_18.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200506002734/Python-06-05-2020-00_23_18.mp4)</video>