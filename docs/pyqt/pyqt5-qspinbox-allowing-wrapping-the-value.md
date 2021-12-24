# PyQt5 QSpinBox–允许包装值

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-允许包装值/](https://www.geeksforgeeks.org/pyqt5-qspinbox-allowing-wrapping-the-value/)

在本文中，我们将看到如何制作旋转框来包装值。包装将使从最大值变化值上升到最小值，类似于从最小值变化值下降到最大值，就像循环一样。

**注意:**只有设置了最小值和最大值时，换行才有意义。

为了做到这一点，我们对旋转框对象使用`setWrapping`方法。

> **语法:**旋转框。设置环绕(真)
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
        self.spin.setRange(0, 9)

        # setting prefix to spin
        self.spin.setPrefix("PREFIX ")

        # setting suffix to spin
        self.spin.setSuffix(" SUFFIX")

        # making spin box wrapping the value
        self.spin.setWrapping(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-419745-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200528001154/Python-2020-05-28-00-11-24.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200528001154/Python-2020-05-28-00-11-24.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200528001154/Python-2020-05-28-00-11-24.mp4)</video>