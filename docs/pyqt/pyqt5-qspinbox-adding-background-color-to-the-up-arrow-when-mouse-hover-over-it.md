# PyQt5 QSpinBox–当鼠标悬停在向上箭头上时，为其添加背景色

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-添加-背景色-鼠标悬停在上面时指向上箭头/](https://www.geeksforgeeks.org/pyqt5-qspinbox-adding-background-color-to-the-up-arrow-when-mouse-hover-over-it/)

在本文中，我们将看到当鼠标悬停在旋转框上时，如何设置旋转框上箭头的背景颜色。旋转框基本上有三个组成部分一个是行编辑另外两个是上下按钮。向上箭头是向上按钮的内部部分，这种背景颜色只会在鼠标悬停在向上箭头上时出现。

为了做到这一点，我们必须改变与旋转框相关的样式表，下面是样式表代码

```
QSpinBox::up-arrow:hover
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
        # adding background color to the up-arrow when mouse hover over it
        self.spin.setStyleSheet("QSpinBox::up-arrow::hover"
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

<video class="wp-video-shortcode" id="video-411882-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200513023342/Python-13-05-2020-02_33_25.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200513023342/Python-13-05-2020-02_33_25.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200513023342/Python-13-05-2020-02_33_25.mp4)</video>