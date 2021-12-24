# PYqt5 Qcommand link 按钮–检查是否可检查

> 原文:[https://www . geeksforgeeks . org/pyqt5-qcommandlink button-checking-if-it-checkable/](https://www.geeksforgeeks.org/pyqt5-qcommandlinkbutton-checking-if-it-is-checkable/)

在本文中，我们将看到如何检查 QCommandLinkButton 是否可检查，默认情况下它是不可检查的，尽管我们可以借助`setCheckable`方法使其随时可检查，可检查的命令链接按钮在被单击时保持在按下状态，当再次被单击时，它将返回到原始状态。

为此，我们对命令链接按钮对象使用`isCheckable`方法

> **语法:**按钮. isCheckable()
> 
> **论证:**不需要论证
> 
> **返回:**返回 bool

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

        # creating label
        label = QLabel("GeeksforGeeks", self)

        # setting label geometry
        label.setGeometry(100, 100, 200, 40)

        # making label multiline
        label.setWordWrap(True)

        # checking if button is checkable
        value = cl_button.isCheckable()

        # setting text to the label
        label.setText("Checkable ? " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-439124-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200625025741/Python-2020-06-25-02-56-58.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200625025741/Python-2020-06-25-02-56-58.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200625025741/Python-2020-06-25-02-56-58.mp4)</video>