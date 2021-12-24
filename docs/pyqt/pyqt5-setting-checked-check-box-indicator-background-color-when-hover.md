# pyqt 5–悬停时设置选中的复选框指示器背景颜色

> 原文:[https://www . geesforgeks . org/pyqt 5-设置-选中-复选框-指示器-背景-颜色-悬停时/](https://www.geeksforgeeks.org/pyqt5-setting-checked-check-box-indicator-background-color-when-hover/)

在本文中，我们将看到当复选框处于选中状态并且鼠标悬停在其上时，如何设置复选框指示器的背景颜色。为了做到这一点，我们必须更改复选框中的指示器的样式表，以显示选中状态以及鼠标在其上移动的时间。

下面是与复选框对象一起使用的样式表代码。

```
QCheckBox::indicator:checked:hover
{
background-color : red;
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

        # adding background color to the indicator
        # when it is in checked state and mouse hover over it
        checkbox.setStyleSheet("QCheckBox::indicator:checked:hover"
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

<video class="wp-video-shortcode" id="video-392051-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200329192151/Python-29-03-2020-19_17_32.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200329192151/Python-29-03-2020-19_17_32.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200329192151/Python-29-03-2020-19_17_32.mp4)</video>