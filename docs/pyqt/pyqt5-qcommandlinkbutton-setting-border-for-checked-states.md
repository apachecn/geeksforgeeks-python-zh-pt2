# PYqt5 Qcommand link 按钮–设置选中状态的边框

> 原文:[https://www . geeksforgeeks . org/pyqt5-qcommandlink button-设置-检查状态边框/](https://www.geeksforgeeks.org/pyqt5-qcommandlinkbutton-setting-border-for-checked-states/)

在本文中，我们将看到如何根据选中的状态为可检查的 QCommandLinkButton 设置边框。命令链接按钮是一种特殊类型的按钮，它兼具按钮和单选按钮的特性。默认情况下，命令链接按钮没有额外的边框，尽管当它被按下时，我们可以看到边框，我们也可以为它设置自定义边框。

我们可以借助`setCheckable`方法使命令链接按钮可勾选，基本上有两种勾选状态一种是勾选即处于按下状态，另一种是未勾选即处于释放状态。

为了做到这一点，我们将为它设置样式表代码，我们使用`setStyleSheet`方法和命令链接按钮对象，下面是样式表代码

```py
QCommandLinkButton::checked
{
border : 4px solid green;
}
QCommandLinkButton::!checked
{
border : 4px solid red;
}

```

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

        # making it chekable
        cl_button.setCheckable(True)

        # setting geometry
        cl_button.setGeometry(150, 100, 200, 50)

        # setting style sheet
        # setting border to it for checked and unchecked state
        cl_button.setStyleSheet("QCommandLinkButton::checked"
                                "{"
                                "border : 4px solid green;"
                                "}"
                                "QCommandLinkButton::! checked"
                                "{"
                                "border : 4px solid red;"
                                "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-442066-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200630014107/Python-2020-06-30-01-40-37.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200630014107/Python-2020-06-30-01-40-37.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200630014107/Python-2020-06-30-01-40-37.mp4)</video>