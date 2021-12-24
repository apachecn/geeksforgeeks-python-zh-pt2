# PyQt5 qcommandlink 按钮–设置自动默认属性

> 原文:[https://www . geesforgeks . org/pyqt 5-qcommandlink button-setting-auto-default-property/](https://www.geeksforgeeks.org/pyqt5-qcommandlinkbutton-setting-auto-default-property/)

在本文中，我们将看到如何设置 QCommandLinkButton 的自动默认属性。如果此属性设置为 true，则命令链接按钮是自动默认按钮。在某些图形用户界面样式中，默认按钮周围会画有一个额外的框架，最多可达 3 个像素或更多。Qt 自动保持自动默认按钮周围的空间，即自动默认按钮可能有一个稍大的尺寸提示。

为此，我们对命令链接按钮对象使用`setAutoDefault`方法

> **语法:**按钮。设置自动默认值(真)
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
        cl_button.setGeometry(250, 100, 150, 50)

        # making it checkable
        cl_button.setCheckable(True)

        # setting auto default property
        cl_button.setAutoDefault(True)

        # size
        size = QSize(30, 30)

        # setting icon size
        cl_button.setIconSize(size)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-439968-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200626022415/Python-2020-06-26-02-23-39.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200626022415/Python-2020-06-26-02-23-39.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200626022415/Python-2020-06-26-02-23-39.mp4)</video>