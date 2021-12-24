# PyQt5 QSpinBox–按下向上按钮时为其添加背景色

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-添加背景色-向上按钮-按下时/](https://www.geeksforgeeks.org/pyqt5-qspinbox-adding-background-color-to-the-up-button-when-it-get-pressed/)

在这篇文章中，我们将看到如何设置背景颜色的旋转框的向上按钮，当它被按下。旋转框基本上是有三个组成部分一个是行编辑另外两个是上下按钮，向上按钮是用来增加数值的。只有按下向上按钮，背景才会出现。

为了做到这一点，我们必须改变与旋转框相关的样式表，下面是样式表代码

```
QSpinBox::up-button:pressed
{
background-color : blue;
}

```

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

        # setting style sheet of spin box
        # adding background color to the up-button when it get pressed
        self.spin.setStyleSheet("QSpinBox::up-button:pressed"
                                "{"
                                "background-color : blue;"
                                "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-411872-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200513014329/Python-13-05-2020-01_42_57.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200513014329/Python-13-05-2020-01_42_57.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200513014329/Python-13-05-2020-01_42_57.mp4)</video>