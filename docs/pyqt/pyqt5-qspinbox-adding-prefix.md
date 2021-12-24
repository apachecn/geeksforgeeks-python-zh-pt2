# PyQt5 QSpinBox–添加前缀

> 原文:[https://www.geeksforgeeks.org/pyqt5-qspinbox-adding-prefix/](https://www.geeksforgeeks.org/pyqt5-qspinbox-adding-prefix/)

在本文中，我们将看到如何给旋转框添加前缀，前缀基本上是在旋转框的值之前插入的文本，前缀对于旋转框的每个值保持不变，即不可编辑。

为了添加前缀，我们将使用`spin_box.setPrifix`方法。

> **语法:** spin_box.setPrifix(文本)
> 
> **自变量:**以字符串为自变量
> 
> **返回:**无

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
        self.spin.setGeometry(100, 100, 150, 40)

        # adding prefix in combo box
        self.spin.setPrefix("Value of x : ")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/e57b034c39179c6965054962726b3206.png)