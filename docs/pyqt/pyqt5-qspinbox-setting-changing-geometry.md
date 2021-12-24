# PyQt5 QSpinBox–设置/更改几何图形

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-设置-更改-几何/](https://www.geeksforgeeks.org/pyqt5-qspinbox-setting-changing-geometry/)

在这篇文章中，我们将看到如何设置旋转框的几何图形。几何基本上是旋转框的位置和大小。将几何体设置到旋转框可以改变其大小和位置。
为了做到这一点，我们对旋转框对象使用了 setGeometry 方法。

> **语法:** font_metrics.setGeometry(左、上、宽、高)
> **参数:**取四个整数作为参数
> **返回:**不返回

下面是实现

## 蟒蛇 3

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

        # setting range to the spin box
        self.spin.setRange(1, 999999)

        # setting prefix to spin
        self.spin.setPrefix("PREFIX ")

        # setting suffix to spin
        self.spin.setSuffix(" SUFFIX")

        # creating a push button
        push = QPushButton("Press ", self)

        # setting position
        push.move(200, 300)

        # adding action to the push button
        push.clicked.connect(self.do_action)

        # left
        self.left = 20

        # top
        self.top = 20

    def do_action(self):

        # setting geometry to the spin box
        self.spin.setGeometry(self.left, self.top, 200, 40)

        # changing position
        self.left += 10
        self.top += 10

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-418088-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200524011552/Python-2020-05-24-01-15-24.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200524011552/Python-2020-05-24-01-15-24.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200524011552/Python-2020-05-24-01-15-24.mp4)</video>