# PyQt5 QSpinBox–设置拉伸系数

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-setting-stretch-factor/](https://www.geeksforgeeks.org/pyqt5-qspinbox-setting-stretch-factor/)

在这篇文章中，我们将看到如何为旋转框的文本设置拉伸因子，拉伸文本意味着扩展文本而不改变其高度，只增加其宽度。最小拉伸系数为 1，最大拉伸系数为 4000。下面是拉伸的旋转框文本的外观。

![](img/b8b3c9000a4047033771c86b87c01b0b.png)

为了做到这一点，我们对旋转框的 QFont 对象使用`setStretch`方法。

> **语法:**字体. set trech(n)
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

        # setting stretch factor
        font.setStretch(200)

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
![](img/a876f8304116243238eaa4d379836b5b.png)