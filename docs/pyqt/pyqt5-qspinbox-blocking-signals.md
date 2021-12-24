# PyQt5 QSpinBox–阻塞信号

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-blocking-signal/](https://www.geeksforgeeks.org/pyqt5-qspinbox-blocking-signals/)

在本文中，我们将看到如何阻止旋转框的信号，阻止信号意味着与旋转框连接的方法将不会接收到信号，例如，当我们向它添加动作时，当它的值发生变化时，该动作将不起作用。被阻塞时发出的信号不会被缓冲。

**注意:**即使旋转箱的信号被阻断，也会发出`destroyed()`信号

为此，我们使用块信号方法。

> **语法:**旋转框。块信号(真)
> 
> **自变量:**它以布尔为自变量
> 
> **执行的动作:**阻止旋转盒发射信号

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
        self.spin.setGeometry(100, 100, 250, 40)

        # setting prefix to spin
        self.spin.setPrefix("Prefix ")

        # setting suffix to spin
        self.spin.setSuffix(" Suffix")

        # adding action to the spin box
        self.spin.valueChanged.connect(self.do)

        # blocking signals of the spin box
        self.spin.blockSignals(True)

        # creating a label
        self.label = QLabel("Label ", self)

        # setting geometry to the label
        self.label.setGeometry(100, 200, 300, 30)

    # method called by spin box
    def do(self):
        # setting text to the label
        self.label.setText("Action done")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
标签文本没有改变，因为旋转框的信号被阻止，所以他们不能调用数值改变信号

<video class="wp-video-shortcode" id="video-412520-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200514022829/Python-14-05-2020-02_28_01.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200514022829/Python-14-05-2020-02_28_01.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200514022829/Python-14-05-2020-02_28_01.mp4)</video>