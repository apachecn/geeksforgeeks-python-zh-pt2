# PyQt5–鼠标悬停在按钮上时改变按钮的背景颜色

> 原文:[https://www . geesforgeks . org/pyqt 5-鼠标悬停在按钮上时改变背景颜色/](https://www.geeksforgeeks.org/pyqt5-changing-background-color-of-push-button-when-mouse-hover-over-it/)

在本文中，我们将看到如何设置鼠标悬停时按钮的背景颜色。当光标不在按钮上时，它会恢复到默认颜色。

为了做到这一点，我们必须改变样式表，当鼠标悬停在按钮上时，必须添加按钮的背景色。下面是样式表代码。

```py
QPushButton::hover
{
background-color : lightgreen;
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

        # creating push button
        button = QPushButton("Geek Button", self)

        # setting geometry of the push button
        button.setGeometry(200, 150, 100, 40)

        # setting background color to push button when mouse hover over it
        button.setStyleSheet("QPushButton::hover"
                             "{"
                             "background-color : lightgreen;"
                             "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-392027-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200329230318/Python-29-03-2020-23_02_56.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200329230318/Python-29-03-2020-23_02_56.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200329230318/Python-29-03-2020-23_02_56.mp4)</video>