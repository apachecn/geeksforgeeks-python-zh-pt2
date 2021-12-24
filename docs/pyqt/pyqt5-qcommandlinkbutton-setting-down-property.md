# PyQt5 qcommandlink button–设置属性

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcommandlink button-setting-down-property/](https://www.geeksforgeeks.org/pyqt5-qcommandlinkbutton-setting-down-property/)

在本文中，我们将看到如何为 QCommandLinkButton 设置属性。Down 属性控制命令链接按钮是否被按下。如果该属性为真，则按下按钮。如果我们将该属性设置为真，则不会发出信号`pressed`和`clicked`。默认情况下，此属性为 false。

为此，我们对命令链接按钮对象使用`setDown`方法

> **语法:**按钮。设置向下(真)
> 
> **自变量:**它以布尔为自变量
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
        cl_button.setGeometry(250, 100, 200, 50)

        # setting down property
        cl_button.setDown(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-441070-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200628234522/Python-2020-06-28-23-44-58.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200628234522/Python-2020-06-28-23-44-58.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200628234522/Python-2020-06-28-23-44-58.mp4)</video>