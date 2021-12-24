# pyqt 5 qscupbox–设置游标

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-setting-cursor/](https://www.geeksforgeeks.org/pyqt5-qspinbox-setting-cursor/)

在本文中，我们将了解如何将光标设置为旋转框，光标是一种指示器，用于在计算机监视器或其他显示设备上显示用户交互的当前位置，这些显示设备将响应来自文本输入或定点设备的输入。

> 为了做到这一点，我们使用设置光标方法
> **语法:**旋转 _ 框。设置光标(光标)
> 
> **自变量:**它以 QCursor 为自变量
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

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()
window.spin.setFocus()
# start the app
sys.exit(App.exec())
```

**注意:**只有当鼠标在旋转框上时才会出现等待光标，否则会出现正常光标

**输出:**

<video class="wp-video-shortcode" id="video-414028-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200517021527/Python-2020-05-17-02-13-41.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200517021527/Python-2020-05-17-02-13-41.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200517021527/Python-2020-05-17-02-13-41.mp4)</video>