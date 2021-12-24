# PyQt5 qcommandlink button–进入下一个状态

> 原文:[https://www . geesforgeks . org/pyqt5-qcommandlink button-转到下一个状态/](https://www.geeksforgeeks.org/pyqt5-qcommandlinkbutton-going-to-next-state/)

在本文中，我们将看到如何进入可检查的 QCommandLinkButton 的下一个状态。我们可以借助`setCheckable`方法使命令链接按钮可检查，这将使命令链接按钮的两种状态被检查，即按下和取消检查，即释放状态。下一个状态将根据当前状态改变状态。

为此，我们对命令链接按钮对象使用`nextCheckState`方法

> **语法:** button.nextCheckState()
> 
> **论证:**不需要论证
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
        cl_button.setGeometry(250, 100, 200, 50)

        # making button checkable
        cl_button.setCheckable(True)

        # creating a push button
        push = QPushButton("Next State", self)

        # setting geometry to the push button
        push.setGeometry(50, 100, 120, 40)

        # adding action to the push button
        push.clicked.connect(lambda: next_method())

        # method called by push button
        def next_method():

            # going to next state
            cl_button.nextCheckState()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-441066-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200628230845/Python-2020-06-28-23-08-24.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200628230845/Python-2020-06-28-23-08-24.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200628230845/Python-2020-06-28-23-08-24.mp4)</video>