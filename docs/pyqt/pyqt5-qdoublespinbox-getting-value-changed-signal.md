# PyQt5 QDoubleSpinBox–获取值更改信号

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdoublespinbox-get-value-changed-signal/](https://www.geeksforgeeks.org/pyqt5-qdoublespinbox-getting-value-changed-signal/)

在本文中，我们将了解如何获得 QDoubleSpinBox 的值更改信号。用户可以借助鼠标和键盘将任意十进制值(浮点数)设置到 QDoubleSpinBox 中，但有时为了覆盖用户输入的值，需要编程设置值，可以借助`setValue`方法进行设置。当值改变时，会发出这个信号。

为了做到这一点，我们将使用`valueChanged`方法和 QDateTimeEdit 对象。

> **语法:**DD _ spin . value changed . connect(方法)
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

        # creating a label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 80)

        # making label multi line
        label.setWordWrap(True)

        # getting value changed signal of double spin box
        d_spin.valueChanged.connect(lambda: spin_method())

        def spin_method():

            # setting text to the label
            label.setText("Value Changed Signal")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-451447-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200713013011/Python-2020-07-13-01-29-01.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200713013011/Python-2020-07-13-01-29-01.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200713013011/Python-2020-07-13-01-29-01.mp4)</video>