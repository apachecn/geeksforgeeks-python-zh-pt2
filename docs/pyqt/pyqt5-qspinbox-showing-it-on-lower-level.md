# PyQt5 QSpinBox–在下层显示

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-showing-it-on-lower-level/](https://www.geeksforgeeks.org/pyqt5-qspinbox-showing-it-on-lower-level/)

在这篇文章中，我们将看到我们如何在较低的水平，较低的水平意味着它将显示在底部，如果它与一些其他的旋转盒位置碰撞，默认情况下，当我们在相似的位置创建两个旋转盒时，在最后创建的旋转盒将显示在顶部，尽管我们可以改变这一点。

为了做到这一点，我们将使用`lower`方法..

> **语法:**旋转 _ 框.下()
> 
> **论证:**不需要论证
> 
> **返回:**返回无

**注意:**此方法用于结尾创建的旋转框

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
        self.spin.setGeometry(100, 100, 150, 40)

        # setting suffix to spin
        self.spin.setSuffix(" Lower")

        # creating spin box
        self.spin_upper = QSpinBox(self)

        # setting geometry to spin_upper
        self.spin_upper.setGeometry(130, 120, 150, 40)

        # setting suffix to spin_upper
        self.spin_upper.setSuffix(" Upper")

        # making spin_upper lower 
        self.spin_upper.lower()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/ab89378f5b6f59be3bc2351bf3de348d.png)