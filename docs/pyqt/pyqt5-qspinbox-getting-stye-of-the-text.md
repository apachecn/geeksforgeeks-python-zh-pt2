# PyQt5 QSpinBox–获取文本样式

> 原文:[https://www . geesforgeks . org/pyqt5-qspinbox-get-style-of-text/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-stye-of-the-text/)

在本文中，我们将了解如何获得旋转框文本的样式，旋转框的文本有许多可用的样式，例如样式倾斜、样式正常和样式倾斜默认情况下，它的样式设置为样式正常样式。我们可以借助`setStyle`方法为其设置样式

为了做到这一点，我们对旋转框的 QFont 对象使用`style`方法。

> **语法:** font.style()
> 
> **论证:**不需要论证
> 
> **返回:**返回 QFont 样式对象，但打印时显示样式值

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
        self.setGeometry(100, 100, 600, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

        # method for widgets
    def UiComponents(self):
        # creating spin box
        self.spin = QSpinBox(self)

        # setting geometry to spin box
        self.spin.setGeometry(100, 100, 250, 40)

        # setting range to the spin box
        self.spin.setRange(0, 999999)

        # setting prefix to spin
        self.spin.setPrefix("PREFIX ")

        # setting suffix to spin
        self.spin.setSuffix(" SUFFIX")

        # getting font of the spin box
        font = self.spin.font()

        # setting style
        font.setStyle(QFont.StyleOblique)

        # reassigning this font to the spin box
        self.spin.setFont(font)

        # creating a label
        label = QLabel(self)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 60)

        # getting style
        style = font.style()

        # setting text to the label
        label.setText("Current Style value: " + str(style))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/510ae17e9034cd316db6db766066791a.png)