# PyQt5 QSpinBox–获取平均字符宽度

> 原文:[https://www . geesforgeks . org/pyqt5-qspinbox-get-average-character-width/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-average-character-width/)

在本文中，我们将了解如何获得旋转框文本的平均字符宽度。平均字符宽度基本上是所有字符的总和除以字符总数，即字体中字形的平均宽度。

为了做到这一点，我们对旋转框的 QFontMetrics 对象使用`averageCharWidth`方法。

> **语法:**font _ metrics . averagecharwidth()
> 
> **论证:**不需要论证
> 
> **返回:**返回整数

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
        self.spin.setSuffix(" SUFFIX")

        # creating a label
        label = QLabel(self)

        # making label multi line
        label.setWordWrap(True)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 60)

        # getting font metrics
        f_metrics = self.spin.fontMetrics()

        # getting average character width
        avg_width = f_metrics.averageCharWidth()

        # setting text to the label
        label.setText("Average Character width: " + str(avg_width))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/3c82086b212aaec247da7a85b506aa51.png)