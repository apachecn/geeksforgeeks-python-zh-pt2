# PyQt5 QDial–使槽口可见

> 原文:[https://www . geesforgeks . org/pyqt 5-qdial-making-notch-visible/](https://www.geeksforgeeks.org/pyqt5-qdial-making-notch-visible/)

在本文中，我们将看到如何使 QDial 的凹口可见，默认情况下 QDial 的凹口是禁用的，尽管我们可以随时使其可见。凹口基本上是围绕表盘绘制的一系列凹口，用于指示可用值的范围。

为此，我们对 QDial 对象使用`setNotchesVisible`方法

> **语法:**dial . setnotchessvisible(True)
> 
> **自变量:**它以布尔为自变量
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

        # making notch visible
        dial.setNotchesVisible(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-446140-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200706022744/Python-2020-07-06-02-27-17.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200706022744/Python-2020-07-06-02-27-17.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200706022744/Python-2020-07-06-02-27-17.mp4)</video>