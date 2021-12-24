# PyQt5 QSpinBox–设置为只读

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-将其设置为只读/](https://www.geeksforgeeks.org/pyqt5-qspinbox-setting-it-to-read-only/)

在本文中，我们将看到如何使旋转框成为只读的，只读意味着用户不能改变它的值。这类似于禁用旋转框，但是当禁用旋转框时，它的其他属性也会被关闭，但是在只读模式下，没有人可以编辑文本。

为了做到这一点，我们对旋转框对象使用`setReadOnly`方法。

> **语法:**旋转框。设置只读(真)
> 
> **自变量:**它以布尔为自变量
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

        # making spin box read only
        self.spin.setReadOnly(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-418710-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200527014011/Python-2020-05-27-01-39-45.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200527014011/Python-2020-05-27-01-39-45.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200527014011/Python-2020-05-27-01-39-45.mp4)</video>