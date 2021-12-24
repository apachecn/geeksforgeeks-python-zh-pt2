# PyQt5 QSpinBox–获取字体的线宽

> 原文:[https://www . geesforgeks . org/pyqt5-qspinbox-获取字体的线宽/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-the-line-width-of-the-font/)

在本文中，我们将看到如何获得旋转框字体的线宽。线宽是下划线和删除线的宽度，根据字体的磅值进行调整。

为了做到这一点，我们对旋转框的 QFontMetrics 对象使用`lineWidth`方法。

> **语法:** font_metrics.lineWidth()
> 
> **论证:**不需要论证
> 
> **返回:**返回整数。

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

        # setting under line to the font
        font = self.spin.font()
        font.setUnderline(True)
        self.spin.setFont(font)

        # creating a label
        label = QLabel(self)

        # making label multi line
        label.setWordWrap(True)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 60)

        # getting font metrics
        f_metrics = self.spin.fontMetrics()

        # getting line width value
        value = f_metrics.lineWidth()

        # setting text to the label
        label.setText(" Line width : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/d722f2e7a5edfc3e760f7b0202187271.png)