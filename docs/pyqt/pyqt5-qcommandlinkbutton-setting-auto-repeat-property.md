# PyQt5 qcommandlink 按钮–设置自动重复属性

> 原文:[https://www . geesforgeks . org/pyqt 5-qcommandlink button-setting-auto-repeat-property/](https://www.geeksforgeeks.org/pyqt5-qcommandlinkbutton-setting-auto-repeat-property/)

在本文中，我们将看到如何设置 QCommandLinkButton 的自动重复属性。如果启用了自动重复属性，则当命令链接按钮按下时，`pressed`、`released`和`clicked`信号会定期发出。默认情况下，自动重复属性处于关闭状态。初始延迟和重复间隔由`autoRepeatDelay`和`autoRepeatInterval`方法以毫秒为单位定义。

为此，我们对命令链接按钮对象使用`setAutoRepeat`方法

> **语法:**按钮。设置自动重复(真)
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

        # setting auto repeat
        cl_button.setAutoRepeat(True)

        # creating label
        label = QLabel("GeeksforGeeks", self)

        # setting label geometry
        label.setGeometry(100, 100, 200, 40)

        # counter
        self.counter = 0

        # adding action to the button
        cl_button.clicked.connect(lambda: update_label())

        # method for updating label text
        def update_label():

            # setting label text
            label.setText(str(self.counter))

            # incrementing the counter
            self.counter += 1

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-441085-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200627035055/Python-2020-06-27-03-50-16.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200627035055/Python-2020-06-27-03-50-16.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200627035055/Python-2020-06-27-03-50-16.mp4)</video>