# PyQt5 QSpinBox–获取焦点链中的下一个小部件

> 原文:[https://www . geesforgeks . org/pyqt5-qspinbox-get-next-widget-in-focus-chain/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-next-widget-in-focus-chain/)

在本文中，我们将看到如何获得旋转框的下一个焦点链小部件。旋转框由两个子部件组成，一个是行编辑，另一个是箭头按钮。焦点是由小部件设置的，即焦点链，当旋转框获得焦点时，它的一个子部件先于另一个子部件获得焦点。

为了做到这一点，我们对旋转框对象使用`nextInFocusChain`方法。

> **语法:** spin_box.nextInFocusChain()
> 
> **论证:**不需要论证
> 
> **返回:**返回 QWidget 对象

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

        # getting next in focus chain widget
        value = self.spin.nextInFocusChain()

        # setting text to the label
        label.setText("Next widget in focus chain  : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/94a2d7d7a233a536bcbab558acbf66dd.png)