# PyQt5 QSpinBox–如何解除光标

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-如何取消光标设置/](https://www.geeksforgeeks.org/pyqt5-qspinbox-how-to-unset-the-cursor/)

在本文中，我们将了解如何取消设置旋转框的光标，光标是一种指示器，用于在计算机监视器或其他显示设备上显示用户交互的当前位置，这些显示设备将响应来自文本输入或定点设备的输入。我们用`setCursor`方法给它设置新的光标。

> 为此，我们使用 onsetcursor 方法
> 
> **语法:** spin_box.unsetCursor()
> 
> **论证:**不需要论证
> 
> **返回:**返回无

下面是实现

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

        # setting range to the spin box
        self.spin.setRange(0, 999999)

        # setting prefix to spin
        self.spin.setPrefix("Prefix ")

        # setting suffix to spin
        self.spin.setSuffix(" Suffix")

        # creating a cursor
        cursor = Qt.WaitCursor

        # setting cursor to the spin box
        self.spin.setCursor(cursor)

        # un-setting the cursor new cursor
        self.spin.unsetCursor()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()
window.spin.setFocus()
# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-414033-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200517023144/Python-2020-05-17-02-31-26.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200517023144/Python-2020-05-17-02-31-26.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200517023144/Python-2020-05-17-02-31-26.mp4)</video>