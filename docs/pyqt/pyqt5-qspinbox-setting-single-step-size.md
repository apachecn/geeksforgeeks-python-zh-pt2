# PyQt5 QSpinBox–设置单步尺寸

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-setting-单步执行-size/](https://www.geeksforgeeks.org/pyqt5-qspinbox-setting-single-step-size/)

在本文中，我们将看到如何设置旋转框的单步大小，默认情况下，当我们创建旋转框时，它的步长是 1。步长基本上是递增或递减的大小。

为了做到这一点，我们将使用`setSingleStep`方法。

> **语法:**旋转框.设置单步(步骤)
> 
> **自变量:**以整数为自变量
> 
> **返回:**无

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
        self.spin.setGeometry(100, 100, 150, 40)

        # setting single step size
        self.spin.setSingleStep(5)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-407288-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200502022604/Python-02-05-2020-02_25_41.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200502022604/Python-02-05-2020-02_25_41.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200502022604/Python-02-05-2020-02_25_41.mp4)</video>