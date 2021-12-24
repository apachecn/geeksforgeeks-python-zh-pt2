# PyQt5–鼠标悬停时的中间复选框背景

> 原文:[https://www . geeksforgeeks . org/pyqt 5-中间-复选框-背景-鼠标悬停时/](https://www.geeksforgeeks.org/pyqt5-intermediate-check-box-background-when-mouse-hovering/)

在本文中，我们将看到如何设置背景颜色的复选框标签部分时，鼠标悬停和它目前处于中间状态。中间状态是介于已检查状态和未检查状态之间的状态，是借助`setTristate`方法创建的第三个状态。

为了做到这一点，我们必须更改复选框的样式表，并在鼠标悬停在中间状态时为其添加背景色。下面是样式表代码。

```py
QCheckBox::indeterminate:hover
{
background-color : cyan;
}

```

下面是实现。

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
        # creating the check-box
        checkbox = QCheckBox('Geek ?', self)

        # setting tristate check box
        checkbox.setTristate(True)

        # setting geometry of check box
        checkbox.setGeometry(200, 150, 100, 30)

        # adding background color to the check box label part
        # when it is in intermediate state when mouse hover over it
        checkbox.setStyleSheet("QCheckBox:indeterminate:hover"
                               "{"
                               "background-color : cyan;"
                               "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-392139-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200330194720/Python-30-03-2020-19_45_51.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200330194720/Python-30-03-2020-19_45_51.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200330194720/Python-30-03-2020-19_45_51.mp4)</video>