# pyqt 5 qscupbox–本地推出

> 哎哎哎:# t0]https://www . geeksforgeeks . org/pyqt 5-qsparabolox-getting-local/

在本文中，我们将了解如何获取旋转框的区域设置。只要没有设置特殊的区域设置，微调框的区域设置要么是父控件的区域设置，要么如果给定的微调框是顶级小部件，那么它就有自己的默认区域设置。

为了做到这一点，我们对旋转框对象使用`locale`方法。

> **语法:** spin_box.locale()
> 
> **论证:**不需要论证
> 
> **返回:**返回 QLocale 对象

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

        # creating a label
        label = QLabel(self)

        # making the label multi line
        label.setWordWrap(True)

        # setting geometry to the label
        label.setGeometry(100, 200, 200, 60)

        # getting the locale of the spin box
        value = self.spin.locale()

        # setting text to the label
        label.setText("Locale : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/27ad5e3cc2468f463e1f0884b807d4bc.png)