# PyQt5 QSpinBox–设置姓氏

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-setting-family-name/](https://www.geeksforgeeks.org/pyqt5-qspinbox-setting-family-name/)

在本文中，我们将了解如何将家族名称设置为旋转框的字体。家族名称也可以选择性地包括铸造名称，例如“Helvetica[克罗尼克斯]”。如果该系列可从多个铸造厂获得，并且铸造厂未指定，则选择任意铸造厂。如果该系列不可用，将使用字体匹配算法设置一个系列。

> 为了做到这一点，我们用旋转框的 QFont 对象设置 Family 方法
> 
> **语法:**字体. setFamily(名称)
> 
> **自变量:**以字符串为自变量
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
        self.spin.setPrefix("PREFIX ")

        # setting suffix to spin
        self.spin.setSuffix(" SUFFIX")

        # getting font of the spin box
        font = QFont('Arial')

        # setting font family name
        font.setFamily("Spin box font_family")

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
![](img/6e81f6e1dfc184f3ebcc13d663db31c0.png)