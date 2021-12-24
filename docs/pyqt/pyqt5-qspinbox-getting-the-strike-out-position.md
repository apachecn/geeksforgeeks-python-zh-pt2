# PyQt5 QSpinBox–获得击出位置

> 原文:[https://www . geesforgeks . org/pyqt5-qspinbox-获得击出位置/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-the-strike-out-position/)

在本文中，我们将看到如何获得旋转框文本的删除线位置。删除线位置是从基线到应该绘制删除线的位置的距离。删除线是一种排字方式，用一条水平线穿过单词的中心，产生这样的文本。与经过审查或净化的文本相反，这些文字仍然可读。这个演示意味着两个意思之一。

为了做到这一点，我们对旋转框的 QFontMetrics 对象使用`strikeOutPos`方法。

> **语法:** font_metrics .删除线()
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

        # getting the strike out position
        value = f_metrics.strikeOutPos()

        # setting text to the label
        label.setText("Strike out position : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/4a61c03521682dac39fec834a3121f2b.png)