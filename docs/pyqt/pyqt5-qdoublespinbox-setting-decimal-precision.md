# PyQt5 QDoubleSpinBox–设置小数精度

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdoublespinbox-setting-decimal-precision/](https://www.geeksforgeeks.org/pyqt5-qdoublespinbox-setting-decimal-precision/)

在本文中，我们将了解如何设置 QDoubleSpinBox 的小数精度。默认情况下，双旋转框的小数精度是 2，尽管我们可以随时更改它。小数精度是数字中小数点右边的位数。例如，数字 123.45 的十进制精度为 2。

> 为了做到这一点，我们将使用双旋转框对象的`setDecimals`方法。
> 
> **语法:** dd_spin.setDecimals(n)
> 
> **自变量:**以整数为自变量
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
        self.setGeometry(100, 100, 500, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        # creating double spin box
        d_spin = QDoubleSpinBox(self)

        # setting geometry to the double spin box
        d_spin.setGeometry(100, 100, 150, 40)

        # setting decimal precision
        d_spin.setDecimals(4)

        # step type
        step_type = QAbstractSpinBox.AdaptiveDecimalStepType

        # adaptive step type
        d_spin.setStepType(step_type)

        # creating a label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 80)

        # making label multi line
        label.setWordWrap(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-455805-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200720022753/Python-2020-07-20-02-27-26.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200720022753/Python-2020-07-20-02-27-26.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200720022753/Python-2020-07-20-02-27-26.mp4)</video>