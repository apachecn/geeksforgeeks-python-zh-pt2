# PyQt5 QSpinBox–鼠标悬停在其上时添加边框

> 原文:[https://www . geesforgeks . org/pyqt5-qspinbox-添加-鼠标悬停时边框-it/](https://www.geeksforgeeks.org/pyqt5-qspinbox-adding-border-when-mouse-hover-over-it/)

在本文中，我们将看到如何在鼠标悬停在旋转框上时为其添加边框，默认情况下，旋转框有一个黑色边框，当鼠标悬停在其上时，该边框不会改变，尽管我们可以改变它。

为了做到这一点，我们必须改变与旋转框相关的样式表代码，下面是样式表代码

```py
QSpinBox::hover
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
        # adding border to the spin box when mouse hover over it
        self.spin.setStyleSheet("QSpinBox::hover"
                                "{"
                                "border : 5px solid blue;"
                                "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-410948-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200512011419/Python-12-05-2020-01_13_59.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200512011419/Python-12-05-2020-01_13_59.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200512011419/Python-12-05-2020-01_13_59.mp4)</video>