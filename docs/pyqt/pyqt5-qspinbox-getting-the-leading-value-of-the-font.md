# PyQt5 QSpinBox–获取字体的前导值

> 原文:[https://www . geeksforgeeks . org/pyqt5-qspinbox-获得领先的字体价值/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-the-leading-value-of-the-font/)

在本文中，我们将了解如何获得旋转框字体的前导值。文本的前导值是指两个文本行基线之间的距离。“行距”一词源于铅字排字机用来均匀分隔文本行的长条。前导这个词已经被卡住了，但本质上它是印刷工对行距的称呼。

为了做到这一点，我们对旋转框的 QFontMetrics 对象使用`leading`方法。

> **语法:** font_metrics.leading()
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

        # creating a label
        label = QLabel(self)

        # making label multi line
        label.setWordWrap(True)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 60)

        # getting font metrics
        f_metrics = self.spin.fontMetrics()

        # getting leading value of the font
        lead = f_metrics.leading()

        # setting text to the label
        label.setText(" Leading Value  : " + str(lead))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/808a00e302428ce5f044731c8d51377b.png)