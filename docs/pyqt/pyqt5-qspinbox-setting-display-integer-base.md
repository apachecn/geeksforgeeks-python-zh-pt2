# PyQt5 QSpinBox–设置显示整数基数

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-设置-显示-整数-基数/](https://www.geeksforgeeks.org/pyqt5-qspinbox-setting-display-integer-base/)

在本文中，我们将了解如何将显示整数基数设置为旋转框，基数或基数是计数系统用来表示数字的不同数字或数字和字母组合的数量。默认的整数基数是 10，尽管我们可以更改它。

**注意:**只有显示整数基数的基数会改变，数值基数会保持 10。

为了做到这一点，我们将使用`spin_box.setDisplayIntegerBase`方法。

> **语法:**自旋盒. setDisplayIntegerBase(n)
> 
> **自变量:**以整数为自变量
> 
> **返回:**无

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

        # setting display integer base
        self.spin.setDisplayIntegerBase(2)

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

<video class="wp-video-shortcode" id="video-405974-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200501001056/Python-01-05-2020-00_09_56.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200501001056/Python-01-05-2020-00_09_56.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200501001056/Python-01-05-2020-00_09_56.mp4)</video>