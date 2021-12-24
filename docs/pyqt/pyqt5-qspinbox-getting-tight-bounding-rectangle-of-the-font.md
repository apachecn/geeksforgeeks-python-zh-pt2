# PyQt5 QSpinBox–获得字体的紧密边框

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-变紧-字体边框/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-tight-bounding-rectangle-of-the-font/)

在本文中，我们将看到如何获得旋转框字体的紧密边框，即文本。边框始终至少覆盖文本在(0，0)处绘制时将覆盖的像素集。

**注意:**换行符作为普通字符处理，不作为换行符处理。

为了做到这一点，我们对旋转框的 QFontMetrics 对象使用`tightBoundingRect`方法。

> **语法:** font_metrics .紧密绑定矩形(文本)
> 
> **自变量:**以字符串为自变量
> 
> **返回:**返回 QRect 对象。

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
        self.spin.setRange(1, 999999)

        # setting prefix to spin
        self.spin.setPrefix("PREFIX ")

        # setting suffix to spin
        self.spin.setSuffix(" SUFFIX")

        # setting strike out to the font
        font = self.spin.font()
        font.setStrikeOut(True)
        self.spin.setFont(font)

        # creating a label
        label = QLabel(self)

        # making label multi line
        label.setWordWrap(True)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 60)

        # getting font metrics
        f_metrics = self.spin.fontMetrics()

        # text
        text = self.spin.text()

        # getting the tight bounding rectangle 
        value = f_metrics.tightBoundingRect(text)

        # setting text to the label
        label.setText("Tight Rectangle : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/32c0dcdd5af7221d77b9730d119caeac.png)