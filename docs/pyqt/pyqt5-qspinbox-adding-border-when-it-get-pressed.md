# PyQt5 QSpinBox–按下时添加边框

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-添加-边框-按下时/](https://www.geeksforgeeks.org/pyqt5-qspinbox-adding-border-when-it-get-pressed/)

在本文中，我们将看到如何在旋转框被按下时为其添加边框，按下旋转框意味着当任何箭头按钮被按下时，只会出现自定义边框。

为了做到这一点，我们必须改变与旋转框相关的样式表代码，下面是样式表代码

```py
QSpinBox::pressed
{
border : 5px solid green;
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

        # setting style sheet to the spin box
        # adding border to the spin box when it get pressed
        self.spin.setStyleSheet("QSpinBox::pressed"
                                "{"
                                "border : 5px solid green;"
                                "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-410955-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200512012140/Python-12-05-2020-01_21_20.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200512012140/Python-12-05-2020-01_21_20.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200512012140/Python-12-05-2020-01_21_20.mp4)</video>