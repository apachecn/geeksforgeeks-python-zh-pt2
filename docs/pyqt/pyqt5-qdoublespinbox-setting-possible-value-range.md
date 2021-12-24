# PyQt5 QDoubleSpinBox–设置可能值范围

> 原文:[https://www . geesforgeks . org/pyqt 5-qdoublespinbox-设置-可能值-范围/](https://www.geeksforgeeks.org/pyqt5-qdoublespinbox-setting-possible-value-range/)

在本文中，我们将了解如何将可能的值范围设置为 QDoubleSpinBox。默认情况下，可能值的范围是从 0 到 100，尽管我们可以分别借助`setMinimum`和`setMaximum`方法单独设置最小和最大可能值。设置范围允许用户输入那些在给定范围内的值，否则不会输入。

> 为了做到这一点，我们将使用双旋转框对象的`setRange`方法。
> 
> **语法:** dd_spin.setRange(m，n)
> 
> **自变量:**取两个浮点值作为自变量
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
        d_spin.setDecimals(1)

        # step type
        step_type = QAbstractSpinBox.AdaptiveDecimalStepType

        # adaptive step type
        d_spin.setStepType(step_type)

        # setting range to the double spin box
        d_spin.setRange(11.1, 13.4)

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

<video class="wp-video-shortcode" id="video-457848-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200723012638/Python-2020-07-23-01-26-18.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200723012638/Python-2020-07-23-01-26-18.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200723012638/Python-2020-07-23-01-26-18.mp4)</video>