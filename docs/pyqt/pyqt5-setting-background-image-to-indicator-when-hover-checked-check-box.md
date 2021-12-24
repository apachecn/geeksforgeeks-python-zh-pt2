# pyqt 5–选中悬停时将背景图像设置为指示器复选框

> 原文:[https://www . geesforgeks . org/pyqt 5-设置-背景-图像-悬停时指示器-选中-复选框/](https://www.geeksforgeeks.org/pyqt5-setting-background-image-to-indicator-when-hover-checked-check-box/)

在这篇文章中，我们将看到如何设置背景图像的指标复选框时，它是在选中状态和鼠标悬停它。为了做到这一点，我们必须更改复选框中的指示器的样式表，以显示选中状态以及鼠标在其上移动的时间。

下面是样式表代码。

```
QCheckBox::indicator:checked:hover
{
background-image : url(image.png);
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
        checkbox.setGeometry(200, 150, 100, 60)

        # changing size of indicator
        # adding background image to the indicator
        # when it is in checked state and mouse hover over it
        checkbox.setStyleSheet("QCheckBox::indicator"
                               "{"
                               "width : 60px;"
                               "height : 60px;"
                               "}"
                               "QCheckBox::indicator:checked:hover"
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

<video class="wp-video-shortcode" id="video-392059-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200329234835/Python-29-03-2020-23_45_54.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200329234835/Python-29-03-2020-23_45_54.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200329234835/Python-29-03-2020-23_45_54.mp4)</video>