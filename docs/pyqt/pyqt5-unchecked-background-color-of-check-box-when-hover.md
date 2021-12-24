# PyQt5–悬停时复选框的未选中背景颜色

> 原文:[https://www . geeksforgeeks . org/pyqt 5-未选中-背景-复选框颜色-悬停时/](https://www.geeksforgeeks.org/pyqt5-unchecked-background-color-of-check-box-when-hover/)

在本文中，我们将看到当鼠标悬停在标签部分的复选框上并且它处于当前未选中状态时，如何为其设置背景颜色。

为了做到这一点，我们必须改变复选框的样式表，并且当鼠标悬停在复选框上时，必须为未握手状态添加背景色。下面是样式表代码。

```
QCheckBox::unchecked:hover
{
background-color : pink;
}

```

下面是实现。

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
        # creating the check-box
        checkbox = QCheckBox('Geek ?', self)

        # setting geometry of check box
        checkbox.setGeometry(200, 150, 100, 30)

        # adding background color to the check box label part
        # when it is in unchecked state when mouse hover over it
        checkbox.setStyleSheet("QCheckBox::unchecked:hover"
                               "{"
                               "background-color : pink;"
                               "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-392127-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200330015210/Python-30-03-2020-01_51_31.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200330015210/Python-30-03-2020-01_51_31.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200330015210/Python-30-03-2020-01_51_31.mp4)</video>