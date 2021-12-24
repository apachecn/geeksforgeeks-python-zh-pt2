# PyQt5 QSpinBox–设置风格提示

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-setting-style-hint/](https://www.geeksforgeeks.org/pyqt5-qspinbox-setting-style-hint/)

在本文中，我们将看到如何设置旋转框文本的样式提示。如果选定的字体系列不可用，字体匹配算法将使用样式提示来查找合适的默认系列。旋转框提供了许多风格提示，如 AnyStyle、SansSerif、Times 等。
为了做到这一点，我们对旋转框的 QFont 对象使用了 setStyleHint 方法。

> **语法:**font . setStyleHint(style _ hint，style_preference)
> **参数:**它以 style hint 作为参数，第二个参数是可选的，是首选项
> **返回:**它返回 None

下面是实现

## 蟒蛇 3

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

        # setting style Hint
        font.setStyleHint(QFont.Serif, QFont.PreferOutline)

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

![](img/07836815141072842a081943fc934bf1.png)