# PyQt5 QSpinBox–编辑完成信号

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-编辑-完成-信号/](https://www.geeksforgeeks.org/pyqt5-qspinbox-editing-finished-signal/)

在本文中我们将看到如何使用旋转框的编辑完成信号，编辑完成是按下回车键时旋转框产生的信号。我们知道，当数值发生变化时，我们可以对微调框采取行动，但是，每次数值发生变化时都不需要调用方法。有时，只有在设置了数值并按下回车键时，即微调框的编辑完成时，才需要调用方法。
为了做到这一点，我们使用 editingFinished.connect 方法。

> **语法:**spin _ box . editing finished . connect(method _ name)
> **参数:**它以方法名作为参数作为参数
> **执行的动作:**它在每次编辑完成时调用传递的方法

下面是实现

## 蟒蛇 3

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

        # setting prefix to spin
        self.spin.setPrefix("Prefix ")

        # setting suffix to spin
        self.spin.setSuffix(" Suffix")

        # creating a label
        self.label = QLabel("Label ", self)

        # setting geometry to the label
        self.label.setGeometry(100, 150, 300, 70)

        # adding action when editing get finished
        self.spin.editingFinished.connect(self.do_action)

    # method called after editing finished
    def do_action(self):

        # getting current value of spin box
        current = self.spin.value()

        self.label.setText("Editing finished, final value : " + str(current))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-413074-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200514195548/Python-14-05-2020-19_55_12.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200514195548/Python-14-05-2020-19_55_12.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200514195548/Python-14-05-2020-19_55_12.mp4)</video>