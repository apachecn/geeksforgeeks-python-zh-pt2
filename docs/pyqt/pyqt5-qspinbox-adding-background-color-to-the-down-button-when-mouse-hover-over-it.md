# PyQt5 QSpinBox–当鼠标悬停在向下按钮上时为其添加背景色

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-添加-背景色-鼠标悬停在按钮上时按下按钮/](https://www.geeksforgeeks.org/pyqt5-qspinbox-adding-background-color-to-the-down-button-when-mouse-hover-over-it/)

在本文中，我们将看到当鼠标悬停在旋转框上时，如何设置旋转框的向下按钮的背景颜色。旋转框基本上有三个组成部分一个是行编辑另外两个是向上和向下按钮，向下按钮用来递减数值。此背景色仅在光标位于旋转框的向下按钮时出现。

为了做到这一点，我们必须改变与旋转框相关的样式表，下面是样式表代码

```
QSpinBox::down-button:hover
{
background-color : red;
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
        # adding background color to the down-button when mouse hover over it
        self.spin.setStyleSheet("QSpinBox::down-button:hover"
                                "{"
                                "background-color : red;"
                                "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-411876-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200513020555/Python-13-05-2020-02_05_35.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200513020555/Python-13-05-2020-02_05_35.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200513020555/Python-13-05-2020-02_05_35.mp4)</video>