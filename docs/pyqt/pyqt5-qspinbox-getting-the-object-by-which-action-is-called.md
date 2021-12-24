# PyQt5 QSpinBox–获取调用动作的对象

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-get-object-by-action-is-call/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-the-object-by-which-action-is-called/)

在本文中，我们将看到如何获得调用动作的旋转框对象。假设当多个旋转框调用同一个动作(方法)时，我们不知道哪个旋转框动作被调用。为了得到调用动作的旋转盒，我们必须跟踪旋转盒发出的信号，因为信号发出时会调用动作。

为了做到这一点，我们对旋转框对象使用`sender`方法。

> **语法:** spin_box.sender()
> 
> **论证:**不需要论证
> 
> **返回:**返回发出信号的 QSpinBox 对象

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

        # adding action to the spin box
        self.spin.valueChanged.connect(self.do_something)

        # creating another spin box
        self.spin2 = QSpinBox(self)

        # setting geometry
        self.spin2.setGeometry(150, 50, 100, 40)

        # adding same action to it
        self.spin2.valueChanged.connect(self.do_something)

        # creating a label
        self.label = QLabel(self)

        # making label multi line
        self.label.setWordWrap(True)

        # setting label geometry
        self.label.setGeometry(100, 200, 250, 60)

    def do_something(self):

        # getting the sender
        sender = self.spin.sender()

        # setting text to the spin box
        self.label.setText(str(sender))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-418702-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200527000152/Python-2020-05-27-00-01-26.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200527000152/Python-2020-05-27-00-01-26.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200527000152/Python-2020-05-27-00-01-26.mp4)</video>