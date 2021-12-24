# PyQt5 QSpinBox–获取框架尺寸

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-get-the-frame-size/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-the-frame-size/)

在本文中，我们将了解如何获得旋转框的帧大小。框架大小是相对于其父框架(包括任何窗口框架)的旋转框大小。默认情况下，旋转框的框架大小包含一个值，该值取决于用户的平台和屏幕几何形状。

为了做到这一点，我们对旋转框对象使用`frameSize`方法。

> **语法:** font_metrics.frameSize()
> 
> **论证:**不需要论证
> 
> **返回:**返回 QSize 对象

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

        # getting the frame size
        f_size = self.spin.frameSize()

        # setting text to the label
        label.setText(str(f_size))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/0cf4ceeab863877955b34c7c89a9a350.png)