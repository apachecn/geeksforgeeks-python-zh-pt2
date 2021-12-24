# PyQt5–复选框

中未勾选指示器的背景色

> 原文:[https://www . geesforgeks . org/pyqt 5-背景色-未选中-复选框中的指示器/](https://www.geeksforgeeks.org/pyqt5-background-color-of-un-checked-indicator-in-check-box/)

在本文中，我们将看到当复选框处于未选中状态时，如何为其设置背景色。选中后，它将恢复到默认形式，对于未选中的状态，我们可以设置背景颜色。

为了给处于未选中状态的指示器添加背景色，我们必须为处于未选中状态的指示器更改样式表。下面是样式表代码。

```py
QCheckBox::indicator:unchecked
{
background-color : yellow;
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

        # adding background color to the indicator for unchecked state
        checkbox.setStyleSheet("QCheckBox::indicator:unchecked"
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

<video class="wp-video-shortcode" id="video-392019-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200329161114/Python-29-03-2020-16_09_41.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200329161114/Python-29-03-2020-16_09_41.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200329161114/Python-29-03-2020-16_09_41.mp4)</video>