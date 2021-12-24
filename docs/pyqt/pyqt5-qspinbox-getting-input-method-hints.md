# PyQt5 QSpinBox–获取输入法提示

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-get-input-method-hints/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-input-method-hints/)

在本文中，我们将看到如何获得旋转框的输入法提示。输入法提示由输入法用来检索关于输入法应该如何操作的提示。例如，如果 Qt。ImhFormattedNumbersOnly 如果设置了一个标志，输入法可能会更改其视觉组件，以反映只能输入数字。

为了做到这一点，我们对旋转框对象使用`inputMethodHints`方法。

> **语法:**spin _ box . inputmethod tiples()
> 
> **论证:**不需要论证
> 
> **返回:**返回方法提示标志

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
        self.spin.setRange(1, 999999)

        # setting prefix to spin
        self.spin.setPrefix("PREFIX ")

        # setting suffix to spin
        self.spin.setSuffix(" SUFFIX")

        # creating a label
        label = QLabel(self)

        # making the label multi line
        label.setWordWrap(True)

        # setting geometry to the label
        label.setGeometry(100, 200, 200, 60)

        # getting input method hint
        value = self.spin.inputMethodHints()

        # setting text to the label
        label.setText(str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/0fd7ee1f0bd005f0c6a4f18eedd0d207.png)