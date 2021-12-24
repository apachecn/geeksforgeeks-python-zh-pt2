# PyQt5 qcommand link 按钮–分配光标

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcommandlink button-assignment-cursor/](https://www.geeksforgeeks.org/pyqt5-qcommandlinkbutton-assigning-cursor/)

在本文中，我们将看到如何设置，也就是将光标分配给 QCommandLinkButton。分配光标意味着当鼠标光标在命令链接按钮上时，它将呈现新的形状。光标形状基本上是光标图标，用于对动作进行分类。

为此，我们对命令链接按钮对象使用`setCursor`方法

> **语法:**按钮。设置光标(光标)
> 
> **自变量:**它以 QCursor 对象为自变量
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

        # creating a command link button
        cl_button = QCommandLinkButton("Press", self)

        # setting geometry
        cl_button.setGeometry(250, 100, 200, 50)

        # cursor
        cursor = Qt.OpenHandCursor

        # setting cursor
        cl_button.setCursor(cursor)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-441091-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200629023057/Python-2020-06-29-02-30-40.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200629023057/Python-2020-06-29-02-30-40.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200629023057/Python-2020-06-29-02-30-40.mp4)</video>