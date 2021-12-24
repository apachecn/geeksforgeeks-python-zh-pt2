# PyQt5 QSpinBox–根据数值调整大小

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-按值调整大小/](https://www.geeksforgeeks.org/pyqt5-qspinbox-resizing-it-according-to-value/)

在本文中，我们将看到如何根据数值调整旋转框的大小。我们可以借助`setGeometry`方法设置旋转框的尺寸，尽管它也需要位置参数，因为调整它的尺寸是不合适的。

为了做到这一点，我们对旋转框对象使用`resize`方法。

> **语法:**旋转框。调整大小(宽度，高度)
> 
> **自变量:**取两个整数作为自变量
> 
> **返回:**返回无

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
        self.spin.setGeometry(100, 100, 50, 50)

        # setting range to the spin box
        self.spin.setRange(50, 400)

        # adding action to the spin box
        self.spin.valueChanged.connect(self.spin_action)

    def spin_action(self):

        # getting the value of spin box
        value = self.spin.value()

        # resizing the spin box
        self.spin.resize(value, value)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-418420-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200526024716/Python-2020-05-26-02-46-45.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200526024716/Python-2020-05-26-02-46-45.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200526024716/Python-2020-05-26-02-46-45.mp4)</video>