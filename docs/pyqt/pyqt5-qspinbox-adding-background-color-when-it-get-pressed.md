# PyQt5 QSpinBox–按下时添加背景色

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-添加-背景色-按下时/](https://www.geeksforgeeks.org/pyqt5-qspinbox-adding-background-color-when-it-get-pressed/)

在这篇文章中，我们将看到如何设置背景色旋转框时，它被按下，默认情况下旋转框是白色的，虽然按钮是灰色的，但我们可以改变颜色。只有按下任何向上和向下按钮时，此背景颜色才会出现。

为了做到这一点，我们必须改变与旋转框相关的样式表，下面是样式表代码

```py
QSpinBox::pressed
{
border : 1px solid blue;
background-color : lightblue;
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
        # adding background color when it get hpressed
        self.spin.setStyleSheet("QSpinBox::pressed"
                                "{"
                                "border : 1px solid blue;"
                                "background-color : lightblue;"
                                "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-411866-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200513012754/Python-13-05-2020-01_27_09.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200513012754/Python-13-05-2020-01_27_09.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200513012754/Python-13-05-2020-01_27_09.mp4)</video>