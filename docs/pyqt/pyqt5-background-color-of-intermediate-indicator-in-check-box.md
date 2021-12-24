# pyqt 5–复选框

中中间指示器的背景色

> 原文:[https://www . geeksforgeeks . org/pyqt 5-中间指示物背景色复选框/](https://www.geeksforgeeks.org/pyqt5-background-color-of-intermediate-indicator-in-check-box/)

在本文中，我们将看到当复选框处于中间状态时，如何设置复选框的背景色。默认情况下，该复选框只有两种状态，尽管我们也可以创建第三种状态，但这种状态不会被选中或取消选中。介于两者之间，借助`setTristate`方法，这两种状态都称为中间状态。

为了给中间状态的指示器添加背景色，我们必须更改中间状态指示器的样式表。下面是样式表代码。

```
QCheckBox::indicator:indeterminate
{
background-color : blue;
}

```

**注意:**为了看到这一点，我们必须先做出第三种状态，否则它将不起作用。

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

        # creating tri-state check box
        checkbox.setTristate(True)

        # adding background color to the indicator
        # when it is in intermediate state
        checkbox.setStyleSheet("QCheckBox::indicator:indeterminate"
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

<video class="wp-video-shortcode" id="video-392063-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200329194721/Python-29-03-2020-19_42_35.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200329194721/Python-29-03-2020-19_42_35.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200329194721/Python-29-03-2020-19_42_35.mp4)</video>