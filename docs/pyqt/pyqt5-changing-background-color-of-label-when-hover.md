# PyQt5–悬停时更改标签的背景颜色

> 原文:[https://www . geesforgeks . org/pyqt 5-悬停时更改标签背景颜色/](https://www.geeksforgeeks.org/pyqt5-changing-background-color-of-label-when-hover/)

在本文中，我们将看到当光标悬停在标签上时，如何更改标签的背景颜色。当光标出现在标签上时，它会改变颜色，当光标不在标签上时，它会回到默认颜色。

为了做到这一点，我们必须改变与标签对象一起使用的样式表代码，并且当鼠标悬停在其上时必须设置背景色，下面是样式表代码。

```py
QLabel::hover
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

        # creating label
        label = QLabel("Hello Geeks", self)

        # setting geometry of the label
        label.setGeometry(200, 150, 100, 40)

        # setting background color to label when mouse hover over it
        label.setStyleSheet("QLabel::hover"
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

<video class="wp-video-shortcode" id="video-392017-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200329212110/Python-29-03-2020-21_18_01.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200329212110/Python-29-03-2020-21_18_01.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200329212110/Python-29-03-2020-21_18_01.mp4)</video>