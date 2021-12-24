# PyQt5 qcommand link 按钮–获取自动重复延迟时间

> 原文:[https://www . geesforgeks . org/pyqt5-qcommandlink button-get-auto-repeat-delay-time/](https://www.geeksforgeeks.org/pyqt5-qcommandlinkbutton-getting-auto-repeat-delay-time/)

在本文中，我们将了解如何获得 QCommandLinkButton 按钮的自动重复延迟时间。它定义了自动重复开始前的初始延迟(以毫秒为单位)。在自动重复属性中，当命令链接按钮按下时，`pressed`、`released`和`clicked`信号会定期发出。虽然可以借助`setAutoRepeat`方法启用自动重复属性，但默认情况下它是关闭的。借助`setAutoRepeatDelay`方法，可以将延迟时间设置到命令链接按钮。

为此，我们对命令链接按钮对象使用`autoRepeatDelay`方法

> **语法:**button . autopeatdeley()
> 
> **论证:**不需要论证
> 
> **返回:**返回整数

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

        # setting auto repeat
        cl_button.setAutoRepeat(True)

        # setting delay time
        cl_button.setAutoRepeatDelay(1000)

        # creating label
        label = QLabel("GeeksforGeeks", self)

        # setting label geometry
        label.setGeometry(50, 100, 200, 40)

        # getting auto repeat delay time
        value = cl_button.autoRepeatDelay()

        # setting text to the label
        label.setText("Auto Repeat Delay (ms) : " + str(value))

        # counter
        self.counter = 0

        # adding action to the button
        cl_button.clicked.connect(lambda: update_label())

        # method for updating label text
        def update_label():

            # setting label text
            label.setText(str(self.counter))

            # incrementing the counter
            self.counter += 1

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/b2b7b8290b9a8f76434ba2a4bbbd7fa6.png)