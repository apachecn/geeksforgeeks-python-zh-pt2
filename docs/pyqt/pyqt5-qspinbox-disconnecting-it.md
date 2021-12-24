# PyQt5 QSpinBox–断开连接

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-disconnecting-it/](https://www.geeksforgeeks.org/pyqt5-qspinbox-disconnecting-it/)

在本文中，我们将看到如何断开旋转盒，断开旋转盒意味着连接到旋转盒的动作将不会发生，它们将被断开。断开与将动作连接到旋转框完全相反。

> 为此，我们使用断开连接的方法
> 
> **语法:**旋转框.断开()
> 
> **论证:**不需要论证
> 
> **返回:**返回浮动

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
        self.spin.setPrefix("Prefix ")

        # setting suffix to spin
        self.spin.setSuffix(" Suffix")

        # adding action to the spin box
        self.spin.valueChanged.connect(self.do_something)

        # disconnecting the spin box
        self.spin.disconnect()

        # creating label
        self.label = QLabel(self)

        # setting geometry to the label
        self.label.setGeometry(100, 200, 200, 70)

        # making it multi line label
        self.label.setWordWrap(True)

    # action called by spin box 
    def do_something(self):

        # setting text to the label
        self.label.setText("Done Something")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()
window.spin.setFocus()
# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-414133-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200517030213/Python-2020-05-17-03-01-51.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200517030213/Python-2020-05-17-03-01-51.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200517030213/Python-2020-05-17-03-01-51.mp4)</video>