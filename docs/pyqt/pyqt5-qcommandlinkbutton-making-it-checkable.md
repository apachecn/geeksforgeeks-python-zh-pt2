# PyQt5 qcommandlink button–使其可检查

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcommandlink button-making-it-checkable/](https://www.geeksforgeeks.org/pyqt5-qcommandlinkbutton-making-it-checkable/)

在本文中，我们将看到如何检查 QCommandLinkButton，默认情况下，它是不可检查的，尽管我们可以使它随时可检查，可检查的命令链接按钮在被单击时保持按下状态，当再次被单击时，它会返回到原始状态。

为此，我们对命令链接按钮对象使用`setCheckable`方法

> **语法:**按钮。设置可检查(真)
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

        # creating a command link button
        cl_button = QCommandLinkButton("Press", self)

        # setting geometry
        cl_button.setGeometry(250, 100, 150, 50)

        # making it checkable
        cl_button.setCheckable(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-439122-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200625025312/Python-2020-06-25-02-52-45.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200625025312/Python-2020-06-25-02-52-45.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200625025312/Python-2020-06-25-02-52-45.mp4)</video>