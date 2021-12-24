# pyqt 5–在鼠标悬停时设置未选中的复选框指示器背景颜色

> 原文:[https://www . geesforgeks . org/pyqt 5-设置-未选中-复选框-指示器-背景色-鼠标悬停/](https://www.geeksforgeeks.org/pyqt5-setting-unchecked-checkbox-indicator-background-color-on-mouse-hover/)

在本文中，我们将看到当复选框处于未选中状态并且鼠标悬停时，如何为其设置背景色。为了做到这一点，我们必须在复选框中更改指示器的样式表，使其处于未选中状态，并且当鼠标在其上移动时。

下面是与复选框对象一起使用的样式表代码。

```
QCheckBox::indicator:unchecked:hover
{
background-color : yellow;
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
        # when mouse hover over it for unchecked state
        checkbox.setStyleSheet("QCheckBox::indicator:unchecked:hover"
                               "{"
                               "background-color : yellow;"
                               "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-392021-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200329163358/Python-29-03-2020-16_13_38.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200329163358/Python-29-03-2020-16_13_38.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200329163358/Python-29-03-2020-16_13_38.mp4)</video>