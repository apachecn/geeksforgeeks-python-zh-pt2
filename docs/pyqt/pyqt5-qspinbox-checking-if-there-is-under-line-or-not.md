# PyQt5 QSpinBox–检查是否有下线

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-检查是否有下线/](https://www.geeksforgeeks.org/pyqt5-qspinbox-checking-if-there-is-under-line-or-not/)

在本文中，我们将看到如何检查旋转框的文本是否有下划线。下划线，也称为下划线，是书写部分正下方或多或少的水平线。手写或打字文档中使用单下划线和偶尔使用双下划线来强调关键文本。借助`setUnderline`方法，我们可以给旋转框的文本添加下划线。

为了做到这一点，我们对旋转框的 QFont 对象使用`underline`方法。

> **语法:** font.underline()
> 
> **论证:**不需要论证
> 
> **返回:**返回 bools

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

        # setting under line
        font.setUnderline(True)

        # reassigning this font to the spin box
        self.spin.setFont(font)

        # creating a label
        label = QLabel(self)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 60)

        # checking if text has under line
        check = font.underline()

        # setting text to the label
        label.setText("Under line ? : " + str(check))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/20ee47cadfada2a92abea494c17b40f6.png)