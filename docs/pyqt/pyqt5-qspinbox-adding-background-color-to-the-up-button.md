# PyQt5 QSpinBox–为向上按钮

添加背景色

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-添加-背景色-向上按钮/](https://www.geeksforgeeks.org/pyqt5-qspinbox-adding-background-color-to-the-up-button/)

在本文中，我们将看到如何设置旋转框的向上按钮的背景颜色。旋转框基本上是有三个组成部分一个是行编辑另外两个是上下按钮，向上按钮是用来增加数值的。下面是“向上”按钮的背景颜色。

![](img/131ba2eb18ff5b406a4a3a38ac069481.png)

为了做到这一点，我们必须改变与旋转框相关的样式表，下面是样式表代码

```
QSpinBox::up-button
{
background-color : green;
}

```

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

        # setting prefix to spin
        self.spin.setPrefix("Prefix ")

        # setting suffix to spin
        self.spin.setSuffix(" Suffix")

        # setting style sheet of spin box
        # adding background color to the up-button
        self.spin.setStyleSheet("QSpinBox::up-button"
                                "{"
                                "background-color : green;"
                                "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/934fd2d07cec63fb3186b43089963958.png)