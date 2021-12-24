# pyqt 5–更改标签背景颜色，用于反悬停状态

> 原文:[https://www . geeksforgeeks . org/pyqt 5-更改-背景-标签颜色-用于反悬停-状态/](https://www.geeksforgeeks.org/pyqt5-change-background-color-of-label-for-anti-hover-state/)

在本文中，我们将看到当标签处于反悬停状态时，我们如何更改标签的背景颜色，即当光标没有悬停在标签上时，当光标出现在标签上时，它将返回到其默认颜色，当光标不在标签上时，它将更改颜色

为了做到这一点，我们必须改变与标签对象一起使用的样式表代码，并且必须为反悬停设置背景颜色。

以下是样式表代码–

```
QLabel::!hover
{
background-color : lightgreen;
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
        # creating label
        label = QLabel("Hello Geeks", self)

        # setting geometry of the label
        label.setGeometry(200, 150, 100, 40)

        # setting background color to label when 
        # mouse is not hovering over it(anti hover)
        label.setStyleSheet("QLabel::! hover"
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

<video class="wp-video-shortcode" id="video-410967-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200511235820/Python-11-05-2020-23_58_05.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200511235820/Python-11-05-2020-23_58_05.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200511235820/Python-11-05-2020-23_58_05.mp4)</video>