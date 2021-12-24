# PYqt5 Qcommand link button–切换可检查按钮

> 原文:[https://www . geeksforgeeks . org/pyqt5-qcommandlink button-toggling-checkable-button/](https://www.geeksforgeeks.org/pyqt5-qcommandlinkbutton-toggling-checkable-button/)

在本文中，我们将看到如何切换 QCommandLinkButton 按钮。切换意味着改变命令链接按钮的状态，当它被切换时，发出切换信号。默认情况下，它是不可检查的，尽管我们可以借助`setCheckable`方法随时检查它。

为此，我们对命令链接按钮对象使用`toggle`方法

> **语法:**按钮。切换()
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
        cl_button.setGeometry(250, 100, 150, 50)

        # making it checkable
        cl_button.setCheckable(True)

        # toggle signal
        # printing message
        cl_button.toggled.connect(lambda: print("Toggled Signal Emitted"))

        # toggle the button
        cl_button.toggle()
        cl_button.toggle()
        cl_button.toggle()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/8e8fa07814ed720b6b99043c0c921e76.png)

```
Toggled Signal Emitted
Toggled Signal Emitted
Toggled Signal Emitted

```