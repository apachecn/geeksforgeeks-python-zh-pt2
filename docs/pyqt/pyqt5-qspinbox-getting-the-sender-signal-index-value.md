# PyQt5 QSpinBox–获取发送方信号索引值

> 原文:[https://www . geesforgeks . org/pyqt5-qspinbox-get-the-sender-signal-index-value/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-the-sender-signal-index-value/)

在本文中，我们将了解如何获得旋转盒发送器信号索引值。Sender signal index 是调用当前正在执行的 slot 的信号的元方法索引，它是 Sender 返回的类的成员。如果在信号激活的槽外调用，-1 返回。

为了做到这一点，我们对旋转框对象使用`senderSignalIndex`方法。

> **语法:** spin_box.senderSignalIndex()
> 
> **论证:**不需要论证
> 
> **返回:**返回整数值

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
        self.label = QLabel(self)

        # making label multi line
        self.label.setWordWrap(True)

        # setting label geometry
        self.label.setGeometry(100, 200, 250, 60)

        # getting sender signal index
        value = self.spin.senderSignalIndex()

        # setting text to the label
        self.label.setText("Sender Signal Index : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/620a7810b4aaab5038364d38645b3ef0.png)