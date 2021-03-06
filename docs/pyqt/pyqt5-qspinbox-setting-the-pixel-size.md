# PyQt5 QSpinBox–设置像素大小

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-设置像素大小/](https://www.geeksforgeeks.org/pyqt5-qspinbox-setting-the-pixel-size/)

在本文中，我们将看到如何设置旋转框文本的像素大小。像素大小改变文本中每个像素的大小像素值越多，文本放大的越多。

为了做到这一点，我们对旋转框的 QFont 对象使用`setPixelSize`方法

> **语法:**字体. set pixixize(n)
> 
> **自变量:**以整数为自变量
> 
> **返回:**返回无

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

        # setting pixel size
        font.setPixelSize(7)

        # reassigning this font to the spin box
        self.spin.setFont(font)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/57edee895c28625e3d9c0126f4d11c22.png)