# PyQt5 QSpinBox–设置样式名称

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-setting-style-name/](https://www.geeksforgeeks.org/pyqt5-qspinbox-setting-style-name/)

在本文中，我们将看到如何设置旋转框文本的样式名称。当开发人员创建了一个自定义样式并想为它命名以供自己使用时，使用样式名，这样样式名更容易理解。

**注意:**字体匹配时会忽略 style()和 weight()之类的属性，不过如果平台的字体引擎支持的话，可能会在之后进行模拟。

为了做到这一点，我们对旋转框的 QFont 对象使用`setStyleName`方法。

> **语法 ：** 字体.setStyleName（名称）
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
        font = self.spin.font()

        # setting style Name
        font.setStyleName("Geek")

        # reassigning this font to the spin box
        self.spin.setFont(font)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/b12a23be1ccd72da76b36f76d1eb36b2.png)