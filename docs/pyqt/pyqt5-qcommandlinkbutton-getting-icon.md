# PyQt5 qcommandlink 按钮–获取图标

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcommandlink button-get-icon/](https://www.geeksforgeeks.org/pyqt5-qcommandlinkbutton-getting-icon/)

在本文中，我们将看到如何获得 QCommandLinkButton 按钮的图标。默认情况下，一个箭头被设置为命令链接按钮的图标，尽管我们可以在`setIcon`方法的帮助下随时更改它。

为此，我们对命令链接按钮对象使用`icon`方法

> **语法:**按钮. icon()
> 
> **论证:**不需要论证
> 
> **返回:**返回 QIcon 对象

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

        # icon
        icon = QIcon('logo.png')

        # changing icon
        cl_button.setIcon(icon)

        # creating label
        label = QLabel("GeeksforGeeks", self)

        # setting label geometry
        label.setGeometry(50, 100, 200, 40)

        # making label multiline
        label.setWordWrap(True)

        # getting icon of the button
        value = cl_button.icon()

        # setting text to the label
        label.setText("Icon " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/229c848218e71dbc726697f917a1070a.png)