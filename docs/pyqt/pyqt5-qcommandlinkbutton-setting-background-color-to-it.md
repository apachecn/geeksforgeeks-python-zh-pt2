# PyQt5 qcommandlink button–为其设置背景色

> 原文:[https://www . geesforgeks . org/pyqt5-qcommandlink button-setting-background-color-to-it/](https://www.geeksforgeeks.org/pyqt5-qcommandlinkbutton-setting-background-color-to-it/)

在本文中，我们将看到如何为 QCommandLinkButton 设置背景颜色。命令链接按钮是一种特殊类型的按钮，它兼具按钮和单选按钮的特性。默认情况下，命令链接按钮没有额外的背景颜色，尽管我们可以为其设置自定义背景颜色。以下是自定义背景颜色的外观

![](img/164beca1743097a38ec57fc35e5752a7.png)

为了做到这一点，我们将为它设置样式表代码，我们使用`setStyleSheet`方法和命令链接按钮对象，下面是样式表代码

```
QCommandLinkButton
{
background-color : lightgreen;
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
        # cl_button.setCheckable(True)

        # setting geometry
        cl_button.setGeometry(150, 100, 200, 50)

        # setting style sheet
        # setting background color
        cl_button.setStyleSheet("QCommandLinkButton"
                                "{"
                                "border : 1px solid black;"
                                "background-color : lightgreen;"
                                "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/e78c3b8fb9491508b4348fc4b3f78dcb.png)