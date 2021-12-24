# PyQt5 QSpinBox–使旋转框解释文本

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-making-spin-box-explored-the-text/](https://www.geeksforgeeks.org/pyqt5-qspinbox-making-spin-box-interprets-the-text/)

在本文中，我们将看到如何让旋转框解释文本。解读文本意味着检查文本并从中发现必要的信息。如果自上次解释后该值发生了变化，那么将发出信号。

为了做到这一点，我们对旋转框对象使用`interpretText`方法。

> **语法:**旋转框.解释文本()
> 
> **论证:**不需要论证
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
        self.spin.setRange(1, 999999)

        # setting prefix to spin
        self.spin.setPrefix("PREFIX ")

        # setting suffix to spin
        self.spin.setSuffix(" SUFFIX")

        # making spin box interprets the text
        self.spin.interpretText()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-418135-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200525020636/Python-2020-05-25-02-06-15.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200525020636/Python-2020-05-25-02-06-15.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200525020636/Python-2020-05-25-02-06-15.mp4)</video>