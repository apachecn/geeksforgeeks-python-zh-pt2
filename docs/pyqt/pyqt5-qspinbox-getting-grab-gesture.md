# PyQt5 QSpinBox–获取抓取手势

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-get-grab-手势/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-grab-gesture/)

在本文中，我们将了解如何将抓取手势设置为旋转框。旋转框有多种抓取手势可供选择:轻按手势、轻按并按住(长按)手势、平移手势、挤压手势、滑动手势和自定义手势。

为了做到这一点，我们对旋转框对象使用`grabGesture`方法。

> **语法:** font_metrics.grabGesture(Qt。点击手势)
> 
> **自变量:**以手势标志为自变量
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

        # setting grab gesture
        self.spin.grabGesture(Qt.TapGesture)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-418092-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200524022251/Python-2020-05-24-02-22-34.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200524022251/Python-2020-05-24-02-22-34.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200524022251/Python-2020-05-24-02-22-34.mp4)</video>