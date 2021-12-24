# PyQt5 qcommand link button–设置图形效果

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcommandlink button-setting-graphics-effects/](https://www.geeksforgeeks.org/pyqt5-qcommandlinkbutton-setting-graphics-effects/)

在本文中，我们将看到如何为 QCommandLinkButton 设置图形效果。图形效果可以是阴影、模糊或颜色效果，这些效果可以随时更改，也可以随时创建新效果。如果此命令链接按钮上已经安装了效果，`QWidget`将在安装新效果之前删除现有效果。

为此，我们对命令链接按钮对象使用`setGraphicsEffect`方法

> **语法:** button.setGraphicsEffect(效果)
> 
> **自变量:**它以 QGraphicEffect 对象为自变量
> 
> **返回:**返回无

**注意:**此方法将效果应用于自身及其所有子对象。

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

        # setting geometry
        cl_button.setGeometry(250, 100, 200, 50)

        # shadow effect
        effect = QGraphicsDropShadowEffect()
        effect.setOffset(20, 20)

        # setting effect to the command link button
        cl_button.setGraphicsEffect(effect)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-441046-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200629021147/Python-2020-06-29-02-11-21.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200629021147/Python-2020-06-29-02-11-21.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200629021147/Python-2020-06-29-02-11-21.mp4)</video>