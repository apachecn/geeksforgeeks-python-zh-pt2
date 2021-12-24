# PyQt5 qcommandlink button–设置按下状态的背景颜色

> 原文:[https://www . geeksforgeeks . org/pyqt5-qcommandlink button-setting-background-color-for-pressed-States/](https://www.geeksforgeeks.org/pyqt5-qcommandlinkbutton-setting-background-color-for-pressed-states/)

在本文中，我们将看到如何根据按下的状态为 QCommandLinkButton 设置背景颜色。命令链接按钮是一种特殊类型的按钮，它兼具按钮和单选按钮的特性。默认情况下，命令链接按钮没有额外的背景颜色，尽管我们可以随时为其设置自定义背景颜色。

基本上有两种按下状态一种是按下状态，即当命令链接按钮被按下时，即被点击，第二种是反按下状态，即当命令链接按钮未被点击时。

为了做到这一点，我们将为它设置样式表代码，我们使用`setStyleSheet`方法和命令链接按钮对象，下面是样式表代码

```py
QCommandLinkButton::pressed
{
background-color : lightgreen;
}
QCommandLinkButton::!pressed
{
background-color : red;
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
        # cl_button.setCheckable(True)

        # setting geometry
        cl_button.setGeometry(150, 100, 200, 50)

        # setting style sheet
        # setting background color according to the pressed state
        cl_button.setStyleSheet("QCommandLinkButton::pressed"
                                "{"
                                "border : 1px solid black;"
                                "background-color : lightgreen;"
                                "}"
                                "QCommandLinkButton::! pressed"
                                "{"
                                "border : 1px solid black;"
                                "background-color : red;"
                                "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-442072-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200630031943/Python-2020-06-30-03-19-16.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200630031943/Python-2020-06-30-03-19-16.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200630031943/Python-2020-06-30-03-19-16.mp4)</video>