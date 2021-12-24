# PyQt5 QSpinBox–获取文本的翻译版本

> 原文:[https://www . geesforgeks . org/pyqt5-qspinbox-get-translated-version-text/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-translated-version-of-text/)

在本文中，我们将了解如何获得文本的翻译版本。文本的翻译版本基于歧义消除字符串和包含复数的字符串的 n 值。如果没有合适的翻译字符串可用，翻译后的文本将是 UTF-8 字符串，即 Unicode 编解码器，可以像 QString 一样表示 Unicode 字符串中的所有字符。但是，UTF-8 可能会出现无效序列，如果发现任何此类序列，它们将被一个或多个“替换字符”替换或抑制。

为了做到这一点，我们对旋转框对象使用`tr`方法。

> **语法:**自旋盒. tr(text，d_text，n)
> 
> **参数:**需要 3 个参数首先一个是文本，另外两个不是强制的首先是消歧字符串，另外一个是引用复数的整数
> 
> **返回:**返回字符串

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

        # setting status tip to the spin box
        self.spin.setStatusTip("Small Value")

        # creating a label
        self.label = QLabel(self)

        # making label multi line
        self.label.setWordWrap(True)

        # setting label geometry
        self.label.setGeometry(100, 200, 250, 60)

        # translating the text
        value = self.spin.tr(self.spin.text())

        # setting text to the label
        self.label.setText("Translated text : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/125f2fea8b57335065c7f530864619b9.png)