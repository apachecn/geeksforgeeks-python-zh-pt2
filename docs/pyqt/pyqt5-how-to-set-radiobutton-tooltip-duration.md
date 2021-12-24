# PyQt5–如何设置单选按钮工具提示持续时间

> 原文:[https://www . geesforgeks . org/pyqt 5-如何设置-radio button-tooltip-duration/](https://www.geeksforgeeks.org/pyqt5-how-to-set-radiobutton-tooltip-duration/)

在本文中，我们将了解如何访问单选按钮的工具提示持续时间。工具提示基本上是我们将鼠标悬停在单选按钮上时出现的消息。它给出提示，帮助用户更好地理解单选按钮。刀尖持续时间基本上就是刀尖出现的时间。

为了访问单选按钮工具提示的内容，我们将使用`toolTipDuration`方法

> **语法:**单选按钮.工具提示持续时间()
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

        # creating a label
        label = QLabel(self)

        # setting geometry of the label
        label.setGeometry(200, 200, 300, 30)

        # accessing the tool tip duration
        duration = self.radio_button.toolTipDuration()

        # printing duration through label
        label.setText("Toll tip duration in millisecond = " + str(duration))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/ae844a6db121a23657264362c235f46f.png)