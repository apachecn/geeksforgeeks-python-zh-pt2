# PyQt5 QSpinBox–越线位置

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-越线-位置/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-over-line-position/)

在本文中，我们将看到如何获得旋转框文本的越行位置。越线位置是从基线到应该绘制越线的位置的距离。over line、overs core 或 over bar 是在文本正上方绘制的水平线的印刷特征。在数学符号中，画线长期以来一直被用作一种纽带，一种表明某些符号属于一起的方式。

为了做到这一点，我们对旋转框的 QFontMetrics 对象使用`overlinePos`方法。

> **语法:**font _ metrics . overlaynepos()
> 
> **论证:**不需要论证
> 
> **返回:**返回整数。

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
        # creating spin box
        self.spin = QSpinBox(self)

        # setting geometry to spin box
        self.spin.setGeometry(100, 100, 250, 40)

        # setting range to the spin box
        self.spin.setRange(1, 999999)

        # setting prefix to spin
        self.spin.setPrefix("PREFIX ")

        # setting suffix to spin
        self.spin.setSuffix(" SUFFIX")

        # setting over line to the font
        font = self.spin.font()
        font.setOverline(True)
        self.spin.setFont(font)

        # creating a label
        label = QLabel(self)

        # making label multi line
        label.setWordWrap(True)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 60)

        # getting font metrics
        f_metrics = self.spin.fontMetrics()

        # getting over line position
        value = f_metrics.overlinePos()

        # setting text to the label
        label.setText("Distance b / w base and over line : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/9d83f9e408bbd433965553392a777320.png)