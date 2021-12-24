# PYqt5 Qcommand link button–设置按下状态的边框

> 原文:[https://www . geeksforgeeks . org/pyqt5-qcommandlink button-设置-按下状态的边框/](https://www.geeksforgeeks.org/pyqt5-qcommandlinkbutton-setting-border-for-pressed-states/)

在本文中，我们将看到如何根据按下的状态为 QCommandLinkButton 设置边框。命令链接按钮是一种特殊类型的按钮，它兼具按钮和单选按钮的特性。默认情况下，命令链接按钮没有额外的边框，尽管当它被按下时，我们可以看到边框，我们也可以为它设置自定义边框。

基本上有两种按下状态一种是按下状态，即当命令链接按钮被按下时，即被点击，第二种是反按下状态，即当命令链接按钮未被点击时。

为了做到这一点，我们将为它设置样式表代码，我们使用`setStyleSheet`方法和命令链接按钮对象，下面是样式表代码

```
QCommandLinkButton::pressed
{
border : 4px solid green;
}
QCommandLinkButton::!pressed
{
border : 2px solid black;
}

```

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

        # setting style sheet
        # setting border to it for pressed and anti pressed state
        cl_button.setStyleSheet("QCommandLinkButton::pressed"
                                "{"
                                "border : 4px solid green;"
                                "}"
                                "QCommandLinkButton::! pressed"
                                "{"
                                "border : 2px solid black;"
                                "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-442062-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200630011113/Python-2020-06-30-01-10-35.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200630011113/Python-2020-06-30-01-10-35.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200630011113/Python-2020-06-30-01-10-35.mp4)</video>