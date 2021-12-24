# PyQt5 QSpinBox–设置输入法提示

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-设置-输入法-提示/](https://www.geeksforgeeks.org/pyqt5-qspinbox-setting-input-method-hints/)

在本文中，我们将看到如何将输入法提示设置到旋转框中。输入法提示由输入法用来检索关于输入法应该如何操作的提示。例如，如果 Qt。ImhFormattedNumbersOnly 如果设置了一个标志，输入法可能会更改其视觉组件，以反映只能输入数字。

为了做到这一点，我们对旋转框对象使用`setInputMethodHints`方法。

> **语法:**spin _ box . setinversiontimehints(Qt)。imhpreferlatin)
> 
> **自变量:**以方法提示为自变量
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
        self.spin.setRange(1, 999999)

        # setting prefix to spin
        self.spin.setPrefix("PREFIX ")

        # setting suffix to spin
        self.spin.setSuffix(" SUFFIX")

        # setting input method hint
        self.spin.setInputMethodHints(Qt.ImhPreferLatin)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/cd373f3bdef1b3655ab906777c0f8041.png)