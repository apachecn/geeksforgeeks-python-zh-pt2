# PyQt5 QSpinBox–为文本增加权重

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-变重为文本/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-weight-to-the-text/)

在本文中，我们将了解如何获得旋转框文本的权重。字体粗细用于设置字体的粗细(粗细)。权重值越大，文本越粗。我们可以借助`setWeight`方法改变字体粗细。

为了做到这一点，我们对旋转框的 QFont 对象使用`weight`方法。

> **语法:** font.weight()
> 
> **论证:**不需要论证
> 
> **返回:**返回整数

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

        # setting weight to the font
        font.setWeight(75)

        # reassigning this font to the spin box
        self.spin.setFont(font)

        # creating a label
        label = QLabel(self)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 60)

        # getting weight of the font
        check = font.weight()

        # setting text to the label
        label.setText("Weight: " + str(check))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/cb2a3578c7f476a791259f69a5951a35.png)