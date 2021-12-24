# PyQt5 qcommandlink button–设置描述文本

> 原文:[https://www . geesforgeks . org/pyqt 5-qcommandlink button-setting-description-text/](https://www.geeksforgeeks.org/pyqt5-qcommandlinkbutton-setting-description-text/)

在本文中，我们将看到如何为 QCommandLinkButton 设置描述文本。描述文本属性包含一个描述性标签来补充命令链接按钮文本。设置此属性将在按钮上设置描述性文本，作为文本标签的补充。这通常会以小于主要文本的字体显示。

为此，我们对命令链接按钮对象使用`setDescription`方法

> **语法:**按钮.设置描述(文本)
> 
> **自变量:**以字符串为自变量
> 
> **返回:**返回无

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

        # text
        text = "GeeksforGeeks"

        # setting description text
        cl_button.setDescription(text)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/5ccb0ded63dacbfee58bfc2fa08876d4.png)