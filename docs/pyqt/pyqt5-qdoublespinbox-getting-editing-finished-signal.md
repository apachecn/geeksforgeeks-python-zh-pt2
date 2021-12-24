# PyQt5 QDoubleSpinBox–获得编辑完成信号

> 原文:[https://www . geesforgeks . org/pyqt5-qdoublespinbox-get-editing-finished-signal/](https://www.geeksforgeeks.org/pyqt5-qdoublespinbox-getting-editing-finished-signal/)

在本文中，我们将看到如何获得 QDoubleSpinBox 的编辑完成信号。编辑完成时会发出此信号。当双旋转框失去焦点和按下回车键时，就会发生这种情况。这是一个非常有用的信号，因为它是在用户确认旋转框中的值时发出的。

为了做到这一点，我们将使用`editingFinished`方法和 QDateTimeEdit 对象。

> **语法:**DD _ spin . editing finished . connect(方法)
> 
> **自变量:**以方法为自变量
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

        # getting editing finished  signal of double spin box
        d_spin.editingFinished.connect(lambda: spin_method())

        def spin_method():

            # setting text to the label
            label.setText("Editing Finished Signal Emitted")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-451453-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200713014545/Python-2020-07-13-01-45-18.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200713014545/Python-2020-07-13-01-45-18.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200713014545/Python-2020-07-13-01-45-18.mp4)</video>