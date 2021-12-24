# PyQt5 QSpinBox–获取最宽字符的宽度

> 原文:[https://www . geesforgeks . org/pyqt5-qspinbox-获取最宽字符的宽度/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-the-width-of-the-widest-character/)

在本文中，我们将看到如何在旋转框中获得最宽字符的宽度。每个字符消耗不同的宽度，有些宽度较小，有些宽度很大，宽度以像素为单位。

为了做到这一点，我们对旋转框的 QFontMetrics 对象使用`maxWidth`方法。

> **语法:** font_metrics.maxWidth()
> 
> **论证:**不需要论证
> 
> **返回:**返回整数。

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

        # setting under line to the font
        font = self.spin.font()
        font.setUnderline(True)
        self.spin.setFont(font)

        # creating a label
        label = QLabel(self)

        # making label multi line
        label.setWordWrap(True)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 60)

        # getting font metrics
        f_metrics = self.spin.fontMetrics()

        # getting max width
        value = f_metrics.maxWidth()

        # setting text to the label
        label.setText("Max width of character: " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/9e53878fa85bedce91451b73b6bbf6b0.png)