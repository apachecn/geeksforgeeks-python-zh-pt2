# PyQt5 qcommandlink button–设置扁平属性

> 原文:[https://www . geesforgeks . org/pyqt5-qcommandlink button-setting-flat-property/](https://www.geeksforgeeks.org/pyqt5-qcommandlinkbutton-setting-flat-property/)

在本文中，我们将看到如何将平面属性设置为 QCommandLinkButton。此属性保存是否引发命令链接按钮边框。此属性的默认值为 false。如果启用此属性，大多数样式都不会绘制命令链接按钮背景，除非正在按下该按钮。

为此，我们对命令链接按钮对象使用`setFlat`方法

> **语法:**按钮。设置平面(真)
> 
> **自变量:**它以布尔为自变量
> 
> **返回:**不返回

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

        # setting flat property
        cl_button.setFlat(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-441062-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200628222715/Python-2020-06-28-22-26-26.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200628222715/Python-2020-06-28-22-26-26.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200628222715/Python-2020-06-28-22-26-26.mp4)</video>