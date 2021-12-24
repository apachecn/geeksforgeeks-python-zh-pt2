# PyQt5 QSpinBox–当鼠标悬停在向上按钮上时，为其添加背景色

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-添加背景色-鼠标悬停在按钮上时向上按钮/](https://www.geeksforgeeks.org/pyqt5-qspinbox-adding-background-color-to-the-up-button-when-mouse-hover-over-it/)

在本文中，我们将看到当鼠标悬停在旋转框上时，我们如何设置旋转框的向上按钮的背景颜色。旋转框基本上是有三个组成部分一个是行编辑另外两个是上下按钮，向上按钮是用来增加数值的。只有光标在背景上时，背景才会出现

为了做到这一点，我们必须改变与旋转框相关的样式表，下面是样式表代码

```
QSpinBox::up-button:hover
{
background-color : green;
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
        # adding background color to the up-button when mouse hover over it
        self.spin.setStyleSheet("QSpinBox::up-button:hover"
                                "{"
                                "background-color : green;"
                                "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-411870-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200513014000/Python-13-05-2020-01_39_18.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200513014000/Python-13-05-2020-01_39_18.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200513014000/Python-13-05-2020-01_39_18.mp4)</video>