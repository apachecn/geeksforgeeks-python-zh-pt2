# PyQt5–单选按钮工具提示持续时间

> 原文:[https://www . geesforgeks . org/pyqt 5-radio button-tooltip-duration/](https://www.geeksforgeeks.org/pyqt5-radiobutton-tooltip-duration/)

在本文中，我们将了解如何将工具提示持续时间设置为单选按钮。工具提示基本上是当我们将鼠标悬停在单选按钮上时出现的一条消息，工具提示给出了提示并帮助用户更好地了解单选按钮。刀尖持续时间基本上是刀尖出现的时间

为了将工具提示持续时间设置为单选按钮，我们将使用`setToolTipDuration`方法。

> **语法:**单选按钮. setToolTipDuration(n)
> 
> **自变量:**取整数作为自变量，整数指毫秒
> 
> **执行的动作:**将设置单选按钮工具提示的持续时间

以下是实施–

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
        self.setGeometry(100, 100, 600, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for widgets
    def UiComponents(self):
        # creating a radio button
        self.radio_button = QRadioButton("Radio button", self)

        # setting geometry of radio button
        self.radio_button.setGeometry(200, 150, 120, 40)

        # setting tool tip
        self.radio_button.setToolTip("Click to make it check")

        # setting tool tip duration
        self.radio_button.setToolTipDuration(2000)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/8726af9e4acc20529da457e72ee8839c.png)