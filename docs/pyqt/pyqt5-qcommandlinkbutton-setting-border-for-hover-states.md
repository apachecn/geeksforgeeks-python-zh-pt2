# PyQt5 qcommandlink button–设置悬停状态的边框

> 原文:[https://www . geeksforgeeks . org/pyqt5-qcommandlink button-setting-border-for-hover-States/](https://www.geeksforgeeks.org/pyqt5-qcommandlinkbutton-setting-border-for-hover-states/)

在本文中，我们将看到如何根据悬停状态为 QCommandLinkButton 设置边框。命令链接按钮是一种特殊类型的按钮，它兼具按钮和单选按钮的特性。默认情况下，命令链接按钮没有额外的边框，尽管当它被按下时，我们可以看到边框，我们也可以为它设置自定义边框。基本上有两种悬停状态，一种是悬停状态，即鼠标在命令链接按钮上，另一种是反悬停状态，即光标不在命令链接按钮上。

为了做到这一点，我们将为它设置样式表代码，我们使用`setStyleSheet`方法和命令链接按钮对象，下面是样式表代码

```
QCommandLinkButton::hover
{
border : 4px solid green;
}
QCommandLinkButton::!hover
{
border : 2px solid red;
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

        cl_button.setCheckable(True)

        # setting geometry
        cl_button.setGeometry(250, 100, 200, 50)

        # setting style sheet
        # setting border to it for hover and anti hover state
        cl_button.setStyleSheet("QCommandLinkButton::hover"
                                "{"
                                "border : 4px solid green;"
                                "}"
                                "QCommandLinkButton::! hover"
                                "{"
                                "border : 2px solid red;"
                                "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-442064-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200630010114/Python-2020-06-30-01-00-48.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200630010114/Python-2020-06-30-01-00-48.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200630010114/Python-2020-06-30-01-00-48.mp4)</video>