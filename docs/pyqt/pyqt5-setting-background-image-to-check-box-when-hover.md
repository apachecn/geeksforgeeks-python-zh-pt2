# PyQt5–悬停时将背景图像设置为复选框

> 原文:[https://www . geesforgeks . org/pyqt 5-设置-背景-图像到复选框-悬停时/](https://www.geeksforgeeks.org/pyqt5-setting-background-image-to-check-box-when-hover/)

在本文中，我们将看到如何在鼠标悬停在复选框上时将背景图像设置为复选框，默认情况下，没有与之关联的背景图像。只有当鼠标悬停在背景图像上时，背景图像才会出现。

为了给复选框添加背景图像，我们必须更改样式表代码，下面是这样做的样式表代码。

```
QCheckBox::hover
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
        checkbox1 = QCheckBox('Geek ?', self)

        # setting geometry of check box
        checkbox1.setGeometry(200, 150, 100, 40)

        # changing style sheet code of check box
        # adding background image to it when mouse hover over it
        checkbox1.setStyleSheet("QCheckBox::hover"
                                "{"
                                "background-image : url(image.png)"
                                "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-394626-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200403195356/Python-03-04-2020-19_53_36.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200403195356/Python-03-04-2020-19_53_36.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200403195356/Python-03-04-2020-19_53_36.mp4)</video>