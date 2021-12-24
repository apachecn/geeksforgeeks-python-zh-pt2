# pyqt 5–改变按下按钮的颜色

> 原文:[https://www . geesforgeks . org/pyqt 5-改变按下按钮的颜色/](https://www.geeksforgeeks.org/pyqt5-changing-color-of-pressed-push-button/)

在这篇文章中，我们将看到如何让按钮在被按下时做出反应。当按钮获得释放时，它会回到原来的颜色，默认情况下，当按钮获得点击时，它会变成浅蓝色，尽管我们可以改变这种颜色。

为了改变按钮的颜色，我们必须改变按钮的样式表，下面是与按钮对象一起使用的样式表代码。

```
QPushButton::clicked
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

        # creating push button widget
        button = QPushButton("Button ", self)

        # setting geometry
        button.setGeometry(200, 100, 100, 40)

        # adding background color to button
        # and background color to pressed button
        button.setStyleSheet("QPushButton"
                             "{"
                             "background-color : lightblue;"
                             "}"
                             "QPushButton::pressed"
                             "{"
                             "background-color : red;"
                             "}"
                             )

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-391914-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200328224553/Python-28-03-2020-22_42_38.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200328224553/Python-28-03-2020-22_42_38.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200328224553/Python-28-03-2020-22_42_38.mp4)</video>