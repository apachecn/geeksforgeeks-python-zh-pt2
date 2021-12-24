# PyQt5 qcommand link button–切换信号

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcommandlink button-togged-signal/](https://www.geeksforgeeks.org/pyqt5-qcommandlinkbutton-toggled-signal/)

在本文中，我们将看到如何获得 QCommandLinkButton 按钮的切换信号。每当可检查的命令链接按钮改变其状态时，就会发出此信号。默认情况下，它是不可检查的，尽管我们可以借助`setCheckable`方法随时检查它。此外，当它可检查时，它的状态是未检查的，尽管我们可以通过`setChecked`方法以编程方式检查它的状态。

为此，我们对命令链接按钮对象使用`toggled`方法

> **语法:**按钮。切换。连接(方法)
> 
> **自变量:**以方法为自变量
> 
> **执行的动作:**发出点击信号时调用方法

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

        # toggle signal
        # printing mesage
        cl_button.toggled.connect(lambda: print("Toggled Signal Emitted"))

        # making its state checked
        cl_button.setChecked(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-439130-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200625031445/Python-2020-06-25-03-14-18.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200625031445/Python-2020-06-25-03-14-18.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200625031445/Python-2020-06-25-03-14-18.mp4)</video>

```py
Toggled Signal Emitted
Toggled Signal Emitted
Toggled Signal Emitted
Toggled Signal Emitted
Toggled Signal Emitted

```