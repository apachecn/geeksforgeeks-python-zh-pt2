# PyQt5 QSpinBox–获取字母间距

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-get-字母间距/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-letter-spacing/)

在本文中，我们将看到如何在旋转框的文本中获得字母间距，字母间距是两个连续字母之间的距离(间隙)。可以通过指定像素或百分比来更改间距。为了设置间距，我们对旋转框的 QFont 对象使用`setLetterSpacing`方法。

为了做到这一点，我们对旋转框的 QFont 对象使用`letterSpacing`方法

> **语法:** font.letterSpacing()
> 
> **论证:**不需要论证
> 
> **返回:**返回浮点值

**注意:**返回值不会告诉你值是百分比还是百分比

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

        # setting letter spacing
        font.setLetterSpacing(QFont.AbsoluteSpacing, 8)

        # reassigning this font to the spin box
        self.spin.setFont(font)

        # creating a label
        label = QLabel(self)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 60)

        # getting letter spacing in between the text
        space = font.letterSpacing()

        # setting text to the label
        label.setText("Spacing Size : " + str(space))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/5921479f9bbd07225970aa92a47231ad.png)