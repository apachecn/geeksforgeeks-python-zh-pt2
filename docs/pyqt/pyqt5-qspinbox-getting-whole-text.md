# PyQt5 QSpinBox–获取全文

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-get-整篇-text/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-whole-text/)

在这篇文章中，我们将看到我们如何可以得到旋转框的整个文本，整个文本意味着值以及前缀和后缀包括在内。

为了做到这一点，我们使用`text`方法。

> **语法:** spin_box.text()
> 
> **论证:**不需要论证
> 
> **返回:**返回字符串

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

        # get the whole text
        text = self.spin.text()

        # printing the text
        print(text)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

```
Prefix 0 Suffix
```

![](img/a3ffc6f6b1ff36492045e49aac654f88.png)