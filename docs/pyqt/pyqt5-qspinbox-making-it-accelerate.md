# PyQt5 QSpinBox–让它加速

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-making-it-accelerate/](https://www.geeksforgeeks.org/pyqt5-qspinbox-making-it-accelerate/)

在这篇文章中，我们将看到如何使旋转箱加速。加速旋转框意味着在按下步进上/下按钮时加快步进频率。如果旋转框被设置为加速，那么你按住按钮的时间越长，它增加/减少数值的速度就越快。

为了做到这一点，我们对旋转框对象使用`setAccelerated`方法。

> **语法:**旋转框.设置加速(真)
> 
> **自变量:**它以布尔为自变量
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
        self.spin.setGeometry(100, 100, 250, 40)

        # setting range to the spin box
        self.spin.setRange(1, 999999)

        # setting prefix to spin
        self.spin.setPrefix("PREFIX ")

        # setting suffix to spin
        self.spin.setSuffix(" SUFFIX")

        # making spin box accelerate
        self.spin.setAccelerated(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-418139-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200525021431/Python-2020-05-25-02-14-02.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200525021431/Python-2020-05-25-02-14-02.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200525021431/Python-2020-05-25-02-14-02.mp4)</video>