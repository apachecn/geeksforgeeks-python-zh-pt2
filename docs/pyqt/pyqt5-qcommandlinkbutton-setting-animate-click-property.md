# PyQt5 qcommandlink button–设置动画点击属性

> 原文:[https://www . geesforgeks . org/pyqt 5-qcommandlink button-setting-animate-click-property/](https://www.geeksforgeeks.org/pyqt5-qcommandlinkbutton-setting-animate-click-property/)

在本文中，我们将看到如何设置 QCommandLinkButton 的动画点击属性。该属性执行动画点击，即按钮立即按下，几毫秒后释放(默认为 100 毫秒)。在释放按钮之前再次调用此功能会重置释放计时器。

为此，我们对命令链接按钮对象使用`animateClick`方法

> **语法:**按钮.动画点击(n)
> 
> **自变量:**以整数为自变量
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
        cl_button = QCommandLinkButton("GeeksforGeeks", self)

        # setting geometry
        cl_button.setGeometry(200, 100, 200, 50)

        # setting animate click property
        cl_button.animateClick(200)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

<video class="wp-video-shortcode" id="video-439112-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200625002934/Python-2020-06-25-00-29-04.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200625002934/Python-2020-06-25-00-29-04.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200625002934/Python-2020-06-25-00-29-04.mp4)</video>