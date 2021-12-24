# pyqt 5–设置鼠标悬停在中间复选框

上时指示器的背景颜色

> 原文:[https://www . geesforgeks . org/pyqt 5-设置-背景-鼠标悬停时指示器颜色-中间-复选框/](https://www.geeksforgeeks.org/pyqt5-setting-background-color-of-indicator-when-mouse-hover-over-intermediate-check-box/)

在本文中，我们将看到当复选框处于中间状态并且鼠标悬停在其上时，如何为其设置背景色。默认情况下，复选框只有两种状态，尽管我们也可以设置第三种状态，该状态未被选中或未被选中，但借助`setTristate`方法，这两种状态之间的状态被称为中间状态。

为了给中间状态的指示器添加背景色，我们必须更改中间状态指示器的样式表，当光标悬停在它上面时，下面是样式表代码。

```py
QCheckBox::indicator:indeterminate:hover
{
background-color : blue;
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

        # setting geometry of check box
        checkbox.setGeometry(200, 150, 100, 30)

        # creating tri-state check box
        checkbox.setTristate(True)

        # adding background color to the indicator
        # when it is in intermediate state and cursor hover over it
        checkbox.setStyleSheet("QCheckBox::indicator:indeterminate:hover"
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

<video class="wp-video-shortcode" id="video-392065-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200329201341/Python-29-03-2020-20_13_21.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200329201341/Python-29-03-2020-20_13_21.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200329201341/Python-29-03-2020-20_13_21.mp4)</video>