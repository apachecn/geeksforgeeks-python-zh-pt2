# pyqt 5–鼠标悬停时如何设置 CheckBox 指示器的背景图像

> 原文:[https://www . geesforgeks . org/pyqt 5-如何设置复选框背景图像-鼠标悬停时的指示器/](https://www.geeksforgeeks.org/pyqt5-how-to-set-background-image-of-checkbox-indicator-when-mouse-hover/)

在本文中，我们将看到当鼠标悬停在复选框上时，如何将背景图像设置为复选框的指示器。默认情况下，没有与之关联的背景图像。只有当鼠标悬停在背景图像上时，背景图像才会出现。

为了给指示器复选框添加背景图像，我们必须更改样式表代码，下面是这样做的样式表代码。

```
QCheckBox::indicator:hover
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
        # adding background image to indicator when mouse hover over it
        checkbox1.setStyleSheet("QCheckBox::indicator:hover"
                                "{"
                                "background-image : url(image.png);"
                                "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-395439-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200403234202/Python-03-04-2020-23_41_12.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200403234202/Python-03-04-2020-23_41_12.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200403234202/Python-03-04-2020-23_41_12.mp4)</video>