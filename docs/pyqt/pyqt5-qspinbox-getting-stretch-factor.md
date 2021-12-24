# PyQt5 QSpinBox–获得拉伸系数

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-get-stretch-factor/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-stretch-factor/)

在这篇文章中，我们将看到如何为旋转框的文本设置拉伸因子，拉伸文本意味着扩展文本而不改变其高度，只增加其宽度。我们可以借助`setStretch`方法改变拉伸因子。最小拉伸系数为 1，最大拉伸系数为 4000

为了做到这一点，我们对旋转框的 QFont 对象使用`stretch`方法。

> **语法:** font.stretch()
> 
> **论证:**不需要论证
> 
> **返回:**返回整数

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
        font = self.spin.font()

        # setting stretch factor
        font.setStretch(200)

        # reassigning this font to the spin box
        self.spin.setFont(font)

        # creating a label
        label = QLabel(self)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 60)

        # getting stretch factor
        s_factor = font.stretch()

        # setting text to the label
        label.setText("Stretch Factor : " + str(s_factor))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/e9acad5d132c113791d282c28de256d0.png)