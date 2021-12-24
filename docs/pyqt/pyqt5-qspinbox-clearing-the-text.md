# PyQt5 QSpinBox–清除文本

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-clearing-the-text/](https://www.geeksforgeeks.org/pyqt5-qspinbox-clearing-the-text/)

在本文中，我们将看到如何清除文本，即数字显示框的值，清除并不意味着重置值意味着恢复原始值，清除值/文本意味着完全擦除数字显示框的内容。

为了做到这一点，我们将使用`clear()`方法。

> **语法:**自旋 _box.clear()
> 
> **论证:**不需要论证
> 
> **返回:**返回无

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
        self.setGeometry(100, 100, 600, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for widgets
    def UiComponents(self):

        # creating spin box
        self.spin = QSpinBox(self)

        # setting geometry to spin box
        self.spin.setGeometry(100, 100, 150, 40)

        # creating a push button
        button = QPushButton("Click", self)

        # setting geometry to the button
        button.setGeometry(200, 200, 100, 40)

        # adding action ot the push button
        button.pressed.connect(self.do_something)

    # action called by the button
    def do_something(self):

        # clearing the spin box
        self.spin.clear()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-407946-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200505015521/Python-05-05-2020-01_54_56.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200505015521/Python-05-05-2020-01_54_56.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200505015521/Python-05-05-2020-01_54_56.mp4)</video>