# PYqt5 Qcommand link 按钮–更改图标

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcommandlink button-changing-icon/](https://www.geeksforgeeks.org/pyqt5-qcommandlinkbutton-changing-icon/)

在本文中，我们将看到如何更改 QCommandLinkButton 按钮的图标。默认情况下，箭头被设置为命令链接按钮的图标，尽管我们可以随时更改它。

为此，我们对命令链接按钮对象使用`setIcon`方法

> **语法:**按钮.设置图标(Icon)
> 
> **自变量:**以 QIcon 对象为自变量
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

        # icon
        icon = QIcon('logo.png')

        # changing icon
        cl_button.setIcon(icon)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-439134-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200625032729/Python-2020-06-25-03-27-13.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200625032729/Python-2020-06-25-03-27-13.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200625032729/Python-2020-06-25-03-27-13.mp4)</video>