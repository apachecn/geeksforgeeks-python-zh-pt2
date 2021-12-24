# PyQt5 QSpinBox–获取当前值

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-get-current-value/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-current-value/)

在本文中，我们将了解如何获得旋转框的当前值。默认情况下，它的值为 0，尽管用户可以随时更改它，并且我们通过编程使用`setValue`方法来更改它的值。

为了得到自旋盒的值，我们使用`value`方法

> **语法:**自旋.值()
> 
> **论证:**不需要论证
> 
> **返回:**返回整数，即当前值

**实施步骤–**

1.创建旋转盒部件
2。创建一个标签来显示当前值
3。向旋转框
4 添加动作。在动作内部借助`value`方法
5 获取当前值。借助标签显示该值。

以下是实施–

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

        # adding action to the spin box
        self.spin.valueChanged.connect(self.show_result)

        # creating label show result
        self.label = QLabel(self)

        # setting geometry
        self.label.setGeometry(100, 200, 200, 40)

    # method called by spin box
    def show_result(self):

        # getting current value
        value = self.spin.value()

        # setting value of spin box to the label
        self.label.setText("Value : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

window.show()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-405599-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200430150646/Python-30-04-2020-15_06_18.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200430150646/Python-30-04-2020-15_06_18.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200430150646/Python-30-04-2020-15_06_18.mp4)</video>