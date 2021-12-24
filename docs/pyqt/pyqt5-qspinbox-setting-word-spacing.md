# PyQt5 QSpinBox–设置字间距

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-setting-word-spacing/](https://www.geeksforgeeks.org/pyqt5-qspinbox-setting-word-spacing/)

在本文中，我们将看到如何设置旋转框文本之间的单词间距。单词是一组由其他字母用空格隔开的单个字母，单词间距会增加它们之间的空格。

**注意:**将间距设置为较低的值不能减小间距。

为了做到这一点，我们对旋转框的 QFont 对象使用`setWordSpacing`方法。

> **语法:**font . setwordspace(n)
> 
> **自变量:**它以 float 为自变量
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
        self.spin.setPrefix("PREFIX ")

        # setting suffix to spin
        self.spin.setSuffix(" one two")

        # getting font of the spin box
        font = self.spin.font()

        # setting word spacing
        font.setWordSpacing(20)

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
![](img/ad25e87c9b9885cd5bc42fd09878a7d6.png)