# PyQt5 QSpinBox–获取像素大小

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-get-pixel-size/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-pixel-size/)

在本文中，我们将看到如何在旋转框中获得文本的像素大小。像素大小改变文本中每个像素的大小像素值越多，文本放大的越多。我们可以借助`setPixelSize`方法改变像素大小。

为了做到这一点，我们对旋转框的 QFont 对象使用`pixelSize`方法

> **语法:**字体.像素化()
> 
> **论证:**不需要论证
> 
> **返回:**返回整数

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
        self.spin.setRange(0, 999999)

        # setting prefix to spin
        self.spin.setPrefix("PREFIX ")

        # setting suffix to spin
        self.spin.setSuffix(" SUFFIX")

        # getting font of the spin box
        font = self.spin.font()

        # setting pixel size
        font.setPixelSize(7)

        # reassigning this font to the spin box
        self.spin.setFont(font)

        # creating a label
        label = QLabel(self)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 60)

        # getting pixel size
        p_size = font.pixelSize()

        # setting text to the label
        label.setText("Pixel Size : " + str(p_size))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/083350c4ea4565540e1fddfeb7a8b84d.png)