# PyQt5 QSpinBox–设置步骤类型

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-setting-step-type/](https://www.geeksforgeeks.org/pyqt5-qspinbox-setting-step-type/)

在本文中，我们将看到如何将步长类型设置到微调框中，有两种步长类型，即默认的一种是正常递增值，另一种是自适应小数。自适应十进制步长意味着步长将持续调整到当前值的十的一次幂，即如果值为 900，则下一个增量将为 10，如果值等于 1000，则增量将为 100。默认情况下，它被设置为默认的步骤类型，尽管我们可以更改。

为了做到这一点，我们将使用`setStepType`方法

**注意:**这个特性是在 Qt 5.12 中引入的。所以低版本没有这个功能。

> **语法:**
> spin _ box . setstetype(qabstactspinbox . adaptiveleteptype)
> 或
> spin _ box . setstetype(1)
> 
> **参数:**它接受 QAbstractionSpinBox 对象，或者我们可以传递 1，即它的值作为参数
> 
> **返回:**返回无

下面是实现

```
# importing libraries
from PyQt5.QtWidgets import * 
from PyQt5 import QtCore, QtGui
from PyQt5.QtGui import * 
from PyQt5.QtCore import * 
from PyQt5.Qt import PYQT_VERSION_STR

print("PyQt version:", PYQT_VERSION_STR)

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
        self.spin.setRange(0, 10000)

        # setting value
        self.spin.setValue(950)

        # setting step type
        self.spin.setStepType(QAbstractSpinBox.AdaptiveDecimalStepType)

        # creating label
        label = QLabel(self)

        # setting geometry to the label
        label.setGeometry(100, 160, 200, 30)

        # getting single step size
        step = self.spin.singleStep()

        # setting text to the label
        label.setText("Step Size : " + str(step))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-407292-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200502025555/Python-02-05-2020-02_54_27.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200502025555/Python-02-05-2020-02_54_27.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200502025555/Python-02-05-2020-02_54_27.mp4)</video>