# PyQt5 QDial–设置包装属性

> 原文:[https://www . geeksforgeeks . org/pyqt 5-q dial-setting-wrapping-property/](https://www.geeksforgeeks.org/pyqt5-qdial-setting-wrapping-property/)

在本文中，我们将看到如何设置 QDial 的包装属性。默认情况下，当我们创建一个 QDial 时，在最小值和最大值之间有一些空间，我们可以通过启用包装属性来删除这个空间，否则会在 Dial 的底部插入一些空间来分隔有效值范围的末端。

为此，我们对 QDial 对象使用`setWrapping`方法

> **语法:**拨号.设置换行(真)
> 
> **自变量:**它以布尔为自变量
> 
> **返回:**返回无

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

        # enabling wrapping property
        dial.setWrapping(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-446135-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200706040731/Python-2020-07-06-04-07-03.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200706040731/Python-2020-07-06-04-07-03.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200706040731/Python-2020-07-06-04-07-03.mp4)</video>