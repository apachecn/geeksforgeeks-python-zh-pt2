# PyQt5 QSpinBox–鼠标悬停在其上时添加背景色

> 原文:[https://www . geesforgeks . org/pyqt5-qspinbox-添加-背景-鼠标悬停时的颜色-it/](https://www.geeksforgeeks.org/pyqt5-qspinbox-adding-background-color-when-mouse-hover-over-it/)

在本文中，我们将看到当鼠标悬停在旋转框上时，我们如何设置旋转框的背景颜色，默认情况下，旋转框是白色的，虽然按钮是灰色的，但是我们可以更改颜色。只有当光标位于旋转框上时，此背景颜色才会出现。

为了做到这一点，我们必须改变与旋转框相关的样式表，下面是样式表代码

```py
QSpinBox::hover
{
border : 1px solid green;
background-color : lightgreen;
}

```

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

        # setting prefix to spin
        self.spin.setPrefix("Prefix ")

        # setting suffix to spin
        self.spin.setSuffix(" Suffix")

        # setting style sheet of spin box
        # adding background color when mouse hover over it
        self.spin.setStyleSheet("QSpinBox::hover"
                                "{"
                                "border : 1px solid green;"
                                "background-color : lightgreen;"
                                "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-411894-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200513012238/Python-13-05-2020-01_22_00.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200513012238/Python-13-05-2020-01_22_00.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200513012238/Python-13-05-2020-01_22_00.mp4)</video>