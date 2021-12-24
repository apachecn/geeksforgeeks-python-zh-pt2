# PyQt5 qcommand link button–将默认光标设置回

> 原文:[https://www . geesforgeks . org/pyqt 5-qcommandlink button-setting-default-cursor-back/](https://www.geeksforgeeks.org/pyqt5-qcommandlinkbutton-setting-default-cursor-back/)

在本文中，我们将看到如何移除新光标，并将原始光标设置回 QCommandLinkButton。分配光标意味着当鼠标光标在命令链接按钮上时，它将呈现新的形状。光标形状基本上是光标图标，用于对动作进行分类。可以借助`setCursor`方法进行设置。

为此，我们对命令链接按钮对象使用`unsetCursor`方法

> **语法:** button.unsetCursor()
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

        # removing cursor i.e setting back default cursor
        cl_button.unsetCursor()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-441034-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200629023746/Python-2020-06-29-02-37-31.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200629023746/Python-2020-06-29-02-37-31.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200629023746/Python-2020-06-29-02-37-31.mp4)</video>