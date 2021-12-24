# PyQt5 QSpinBox–关闭旋转盒

> 原文:[https://www . geesforgeks . org/pyqt5-qspinbox-closing-the-the-spin-box/](https://www.geeksforgeeks.org/pyqt5-qspinbox-closing-the-spin-box/)

在本文中，我们将看到如何关闭旋转框，同时制作图形用户界面当小部件的使用完成时，需要将小部件从屏幕上移除，这可以通过隐藏它来完成，但最好的方法是关闭小部件。

为了做到这一点，我们将使用`close()`方法。

> **语法:**旋转 _box.close()
> 
> **论证:**不需要论证
> 
> **返回:**返回 bool

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
        self.spin.setGeometry(100, 100, 150, 40)

        # creating a push button
        button = QPushButton("Click", self)

        # setting geometry to the button
        button.setGeometry(200, 200, 100, 40)

        # adding action ot the push button
        button.pressed.connect(self.do_something)

    # action called by the button
    def do_something(self):
        # closing the spin box
        self.spin.close()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-407948-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200505020223/Python-05-05-2020-02_02_08.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200505020223/Python-05-05-2020-02_02_08.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200505020223/Python-05-05-2020-02_02_08.mp4)</video>