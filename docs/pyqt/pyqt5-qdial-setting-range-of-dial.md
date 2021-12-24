# PyQt5 QDial–表盘的设置范围

> 原文:[https://www . geesforgeks . org/pyqt5-qdial-setting-dial-range/](https://www.geeksforgeeks.org/pyqt5-qdial-setting-range-of-dial/)

在本文中，我们将了解如何设置 QDial 的范围。范围意味着上限和下限同时存在，因此用户可以分配任何不在范围内的值。我们可以分别借助`setMinimum`和`setMinimum`方法设置 QDial 的下限和上限。

为此，我们对 QDial 对象使用`setMaximum`方法

> **语法:**拨号.设置范围(最小，最大)
> 
> **自变量:**取两个整数作为自变量
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
        self.setGeometry(100, 100, 500, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        # creating QDial object
        dial = QDial(self)

        # setting geometry to the dial
        dial.setGeometry(100, 100, 100, 100)

        # setting range
        dial.setRange(100, 120)

        # making notch visible
        dial.setNotchesVisible(True)

        # creating a label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry to the label
        label.setGeometry(220, 125, 200, 60)

        # making label multiline
        label.setWordWrap(True)

        # adding action to the dial
        dial.valueChanged.connect(lambda: label.setText("Value = " + str(dial.value())))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-446127-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200706032435/Python-2020-07-06-03-24-14.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200706032435/Python-2020-07-06-03-24-14.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200706032435/Python-2020-07-06-03-24-14.mp4)</video>