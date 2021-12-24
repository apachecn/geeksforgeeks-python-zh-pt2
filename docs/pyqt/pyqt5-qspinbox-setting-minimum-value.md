# PyQt5 QSpinBox–设置最小值

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-setting-minimum-value/](https://www.geeksforgeeks.org/pyqt5-qspinbox-setting-minimum-value/)

在本文中，我们将看到如何设置最小值，即旋转框的下限，默认情况下，当我们创建一个旋转框时，它的范围从 0 到 99，即它的最小值是 0，尽管我们可以更改它。

为了做到这一点，我们将使用`spin_box.setMinimum`方法。

> **语法:**旋转框.设置最小值(n)
> 
> **自变量:**以整数为自变量
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
        self.spin.setGeometry(100, 100, 100, 40)

        # setting minimum value
        self.spin.setMinimum(-10)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-405966-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200501005523/Python-01-05-2020-00_54_26.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200501005523/Python-01-05-2020-00_54_26.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200501005523/Python-01-05-2020-00_54_26.mp4)</video>