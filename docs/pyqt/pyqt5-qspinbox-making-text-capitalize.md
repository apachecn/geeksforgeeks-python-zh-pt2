# PyQt5 QSpinBox–使文本大写

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-making-text-大写/](https://www.geeksforgeeks.org/pyqt5-qspinbox-making-text-capitalize/)

在本文中，我们将看到如何使旋转框的文本大写，以便使用以`QFont`对象为参数的`setFont`方法来设置字体。为了使文本，即字体大写，我们必须获得旋转框的 QFont 对象，然后使其大写，然后将其重新分配给旋转框。

> 为了做到这一点，我们对旋转框的 QFont 对象使用了 set 大写方法
> 
> **语法:**font .set 大写(True)
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

        # making font capitalize
        font.setCapitalization(True)

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
![](img/ab553611b46b6980ff83871f78c12a62.png)