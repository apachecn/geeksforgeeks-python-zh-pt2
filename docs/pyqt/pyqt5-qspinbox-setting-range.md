# PyQt5 QSpinBox–设置范围

> 原文:[https://www.geeksforgeeks.org/pyqt5-qspinbox-setting-range/](https://www.geeksforgeeks.org/pyqt5-qspinbox-setting-range/)

在本文中，我们将看到如何设置旋转框的范围，默认情况下，当我们创建旋转框时，它的范围从 0 到 99 不等，即最小值(下限)为 0，最大值(上限)为 99，尽管我们可以更改此范围。

为了做到这一点，我们将使用`setRange`方法。

> **语法:**旋转框。设置范围(最小值，最大值)
> 
> **自变量:**取两个整数，即最小值和最大值作为自变量
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

        # setting range
        self.spin.setRange(-1, 1)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-407286-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200502020422/Python-02-05-2020-02_03_40.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200502020422/Python-02-05-2020-02_03_40.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200502020422/Python-02-05-2020-02_03_40.mp4)</video>