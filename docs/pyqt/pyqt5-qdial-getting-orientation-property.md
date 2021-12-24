# PyQt5 QDial–获取方向属性

> 原文:[https://www . geesforgeks . org/pyqt 5-qdial-get-orientation-property/](https://www.geeksforgeeks.org/pyqt5-qdial-getting-orientation-property/)

在本文中，我们将看到如何获得 QDial 的方向属性。此属性保持滑块的方向，方向必须是垂直(默认)或水平。垂直方向关联值为 2，水平方向为 1，可以借助`setOrientation`方法设置到 QDial。

为此，我们对 QDial 对象使用`orientation`方法

> **语法:** dial.orientation()
> 
> **论证:**不需要论证
> 
> **返回:**返回方向对象，但打印时显示方向的相关值

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

        # creating QDial object
        dial = QDial(self)

        # setting geometry to the dial
        dial.setGeometry(100, 100, 100, 100)

        # making notch visible
        dial.setNotchesVisible(True)

        # setting orientation to it
        dial.setOrientation(Qt.Horizontal)

        # creating a label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry to the label
        label.setGeometry(220, 125, 200, 60)

        # making label multiline
        label.setWordWrap(True)

        # getting orientation
        value = dial.orientation()

        # setting text to the label
        label.setText("Orientation : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/8e77dd30e09b865378a0fe86914c70dc.png)