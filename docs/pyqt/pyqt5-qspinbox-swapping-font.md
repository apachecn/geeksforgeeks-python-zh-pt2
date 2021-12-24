# pyqt 5 qspinbox–置换字体

> 哎哎哎:# t0]https://www . geeksforgeeks . org/pyqt 5-qscupbox 交换字体/

在本文中，我们将看到如何交换旋转框的字体，交换旋转框的字体意味着用其他 QFont 对象替换旋转框的 QFont 对象。借助`font`方法可以得到旋转框的 QFont 对象。

> 为了做到这一点，我们对旋转框的 QFont 对象使用交换方法
> 
> **语法:**font . swap(other _ font)
> 
> **自变量:**它以 QFont 对象为自变量
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
        self.spin.setPrefix("Prefix ")

        # setting suffix to spin
        self.spin.setSuffix(" Suffix")

        # getting font of the spin box
        font = self.spin.font()

        # another font
        another_font = QFont("Times", 12)

        # swapping current font with another font
        font.swap(another_font)

        # setting back this font to the spin box
        self.spin.setFont(font)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/d9dbfd15b02bd7a40aa45f842f13d5e7.png)