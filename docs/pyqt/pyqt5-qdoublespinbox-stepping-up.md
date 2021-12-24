# pyqt 5 QDoubleSpinBox–加速

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdoublespinbox-升压/](https://www.geeksforgeeks.org/pyqt5-qdoublespinbox-stepping-up/)

在本文中，我们将看到如何以编程方式增加 QDoubleSpinBox 的值。双旋框可以以十进制值作为输入，我们可以借助`setValue`方法设置值，踩下默认只会将值递增 1，如果选择自适应十进制类型，则按十进制递增。

> 为了做到这一点，我们将使用双旋转框对象的`stepUp`方法。
> 
> **语法:** dd_spin.stepUp()
> 
> **论证:**不需要论证
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

        # push button
        push = QPushButton("Press", self)

        # setting geometry to the push button
        push.setGeometry(100, 150, 100, 35)

        # adding action to the push button
        # stepping up the value
        push.clicked.connect(lambda: d_spin.stepUp())

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-455796-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200720020156/Python-2020-07-20-02-01-31.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200720020156/Python-2020-07-20-02-01-31.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200720020156/Python-2020-07-20-02-01-31.mp4)</video>