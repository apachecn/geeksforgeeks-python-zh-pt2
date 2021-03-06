# PyQt5–悬停时设置未选中的复选框指示器背景图像

> 原文:[https://www . geesforgeks . org/pyqt 5-设置-未选中-复选框-指示器-背景-图像-悬停时/](https://www.geeksforgeeks.org/pyqt5-setting-unchecked-check-box-indicator-background-image-when-hover/)

在这篇文章中，我们将看到如何设置背景图像的指标复选框时，它是在未选中状态和鼠标悬停。为了做到这一点，我们必须在复选框中更改指示器的样式表，使其处于未选中状态，并且当鼠标在其上移动时。

下面是样式表代码。

```py
QCheckBox::indicator:unchecked:hover
{
background-image : url(image.png);
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
        checkbox.setGeometry(200, 150, 100, 60)

        # changing size of indicator
        # adding background image to the indicator
        # when it is in unchecked state and mouse hover over it
        checkbox.setStyleSheet("QCheckBox::indicator"
                               "{"
                               "width : 60px;"
                               "height : 60px;"
                               "}"
                               "QCheckBox::indicator:unchecked:hover"
                               "{"
                               "background-image : url(indicator_image.png);"
                               "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-392053-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200329232442/Python-29-03-2020-23_23_25.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200329232442/Python-29-03-2020-23_23_25.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200329232442/Python-29-03-2020-23_23_25.mp4)</video>