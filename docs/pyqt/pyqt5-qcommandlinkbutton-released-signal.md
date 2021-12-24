# PyQt5 qcommand link button–释放信号

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcommandlink button-released-signal/](https://www.geeksforgeeks.org/pyqt5-qcommandlinkbutton-released-signal/)

在本文中，我们将看到如何获得 QCommandLinkButton 的释放信号。释放按钮时会发出此信号。点击按钮有两个阶段，第一个是按下状态，第二个是释放状态。

为此，我们对命令链接按钮对象使用`released`方法

> **语法:** button.released.connect(方法)
> 
> **自变量:**以方法为自变量
> 
> **执行的动作:**发出点击信号时调用方法

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

        # creating label
        label = QLabel("GeeksforGeeks", self)

        # setting label geometry
        label.setGeometry(100, 100, 200, 40)

        # released signal
        # set text to the label
        cl_button.pressed.connect(lambda: label.setText("Released Signal Emitted"))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-439120-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200625024312/Python-2020-06-25-02-42-51.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200625024312/Python-2020-06-25-02-42-51.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200625024312/Python-2020-06-25-02-42-51.mp4)</video>