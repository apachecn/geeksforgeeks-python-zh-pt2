# PyQt5 qcommandlink 按钮–获取帮助文本

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcommandlink button-get-help-text/](https://www.geeksforgeeks.org/pyqt5-qcommandlinkbutton-getting-help-text/)

在本文中，我们将看到如何获取 QCommandLinkButton 的帮助文本。帮助文本是用于告诉其他用户有关命令链接按钮的使用信息的文本。它包含可用于检查用途、限制等的信息。借助`setWhatsThis`方法，可以在命令链接按钮上添加帮助文本。

为此，我们对命令链接按钮对象使用`whatsThis`方法

> **语法:**按钮. whatsThis()
> 
> **论证:**不需要论证
> 
> **返回:**返回字符串

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

        # setting help text
        cl_button.setWhatsThis("Command Link Button for GeeksforGeeks")

        # creating label
        label = QLabel("GeeksforGeeks", self)

        # setting label geometry
        label.setGeometry(50, 100, 200, 80)

        # making label multiline
        label.setWordWrap(True)

        # getting help text
        value = cl_button.whatsThis()

        # setting text to the label
        label.setText("Help Text : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/1abb0f26e8da253a1da10f2801d13a6f.png)