# PyQt5 QSpinBox–加粗文本

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-making-text-bold/](https://www.geeksforgeeks.org/pyqt5-qspinbox-making-text-bold/)

在本文中，我们将看到如何使旋转框的文本加粗，以便设置字体使用以`QFont`对象为参数的`setFont`方法。为了使文本，即字体加粗，我们必须获得旋转框的 QFont 对象，然后使其加粗，然后将其重新分配给旋转框。

> 为了做到这一点，我们对旋转框的 QFont 对象使用了 setBold 方法
> 
> **语法:** font.setBold(True)
> 
> **自变量:**它以布尔为自变量
> 
> **返回:**返回无

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
        self.spin.setPrefix("Prefix ")

        # setting suffix to spin
        self.spin.setSuffix(" Suffix")

        # getting font of the spin box
        font = self.spin.font()

        # making font bold
        font.setBold(True)

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
![](img/09995f6e7aa5cad553d9b2bce1e248ba.png)