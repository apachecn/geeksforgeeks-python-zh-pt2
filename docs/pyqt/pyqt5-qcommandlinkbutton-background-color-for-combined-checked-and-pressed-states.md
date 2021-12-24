# PyQt5 qcommand link button–组合选中和按下状态的背景色

> 原文:[https://www . geeksforgeeks . org/pyqt5-qcommandlink button-背景色-用于组合检查和按下状态/](https://www.geeksforgeeks.org/pyqt5-qcommandlinkbutton-background-color-for-combined-checked-and-pressed-states/)

在本文中，我们将看到如何根据选中和悬停状态的组合来设置可勾选`QCommandLinkButton`的背景颜色。命令链接按钮是一种特殊类型的按钮，它兼具按钮和单选按钮的特性。默认情况下，命令链接按钮没有额外的背景颜色，尽管我们可以随时为其设置自定义背景颜色。

我们可以借助`setCheckable`方法使命令链接按钮可勾选，基本上有两种勾选状态一种是勾选即处于按下状态，另一种是未勾选即处于释放状态。

为了做到这一点，我们将为它设置样式表代码，我们使用`setStyleSheet`方法和命令链接按钮对象，下面是样式表代码

```
QCommandLinkButton::checked
{
background-color : lightgreen;
}
QCommandLinkButton::checked::pressed
{
background-color : yellow;
}
QCommandLinkButton::!checked
{
background-color : red;
}
QCommandLinkButton::!checked::pressed
{
background-color : pink;
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

        # making it chekable
        cl_button.setCheckable(True)

        # setting geometry
        cl_button.setGeometry(150, 100, 200, 50)

        # setting style sheet
        # setting background color according to checked state
        # adding background color for checked pressed state combine
        cl_button.setStyleSheet("QCommandLinkButton::checked"
                                "{"
                                "border : 1px solid black;"
                                "background-color : lightgreen;"
                                "}"
                                "QCommandLinkButton::checked::pressed"
                                "{"
                                "border : 1px solid black;"
                                "background-color : yellow;"
                                "}"
                                "QCommandLinkButton::! checked"
                                "{"
                                "border : 1px solid black;"
                                "background-color : red;"
                                "}"
                                "QCommandLinkButton::! checked::pressed"
                                "{"
                                "border : 1px solid black;"
                                "background-color : pink;"
                                "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-442080-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200630040303/Python-2020-06-30-04-02-38.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200630040303/Python-2020-06-30-04-02-38.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200630040303/Python-2020-06-30-04-02-38.mp4)</video>