# PyQt5 QSpinBox–设置超线

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-setting-over-line/](https://www.geeksforgeeks.org/pyqt5-qspinbox-setting-over-line/)

在这篇文章中，我们将看到如何设置旋转框的文本越线。over line、overs core 或 over bar 是在文本正上方绘制的水平线的印刷特征。下面是带有画线文字的旋转框的外观。

![](img/02ccd197429a40ba7d450466d93609a9.png)

为了做到这一点，我们对旋转框的 QFont 对象使用`setOverline`方法

> **语法:** font.setOverline(True)
> 
> **自变量:**它以布尔为自变量
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

        # setting overline
        font.setOverline(True)

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
![](img/b415cb64f13bb170f0677b586e7a3427.png)