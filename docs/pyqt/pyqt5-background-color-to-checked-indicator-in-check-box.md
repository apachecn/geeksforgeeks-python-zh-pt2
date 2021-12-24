# PyQt5–复选框

中选中指示器的背景颜色

> 原文:[https://www . geesforgeks . org/pyqt 5-背景色-待检查-复选框中的指示器/](https://www.geeksforgeeks.org/pyqt5-background-color-to-checked-indicator-in-check-box/)

在本文中，我们将看到当指示器处于选中状态时，如何为其设置背景颜色，当它未被选中时，其颜色将变为默认颜色。

为了给指示器设置背景颜色，我们必须编辑复选框对象使用的样式表，并且我们必须更改选中指示器的背景颜色。下面是样式表代码。

```py
QCheckBox::indicator:checked
{
background-color : red;
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

        # adding background color to the indicator
        # when it is in checked state
        checkbox.setStyleSheet("QCheckBox::indicator:checked"
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

<video class="wp-video-shortcode" id="video-392025-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200329191054/Python-29-03-2020-19_07_30.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200329191054/Python-29-03-2020-19_07_30.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200329191054/Python-29-03-2020-19_07_30.mp4)</video>