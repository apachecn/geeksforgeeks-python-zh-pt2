# PyQt5 QSpinBox–检查是否有越线

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-检查是否在线/](https://www.geeksforgeeks.org/pyqt5-qspinbox-checking-if-there-is-over-line-or-not/)

在本文中，我们将看到如何检查旋转框的文本是否有多余的行。过线、过芯或过条是在文本正上方画出的水平线的印刷特征。虽然我们可以借助`setOverline`方法设置超线，但是默认情况下文本没有超线。

为了做到这一点，我们对旋转框的 QFont 对象使用`overline`方法

> **语法:** font.overline()
> 
> **论证:**不需要论证
> 
> **返回:**返回 bool

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

        # setting over-line
        font.setOverline(True)

        # reassigning this font to the spin box
        self.spin.setFont(font)

        # creating a label
        label = QLabel(self)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 60)

        # checking if there is over line or not
        check = font.overline()

        # setting text to the label
        label.setText("Over Line ?: " + str(check))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/096fc80d53731a09b5687ce2a31555a5.png)