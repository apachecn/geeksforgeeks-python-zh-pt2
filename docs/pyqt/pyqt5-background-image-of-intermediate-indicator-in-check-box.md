# pyqt 5–复选框

中中间指示器的背景图像

> 原文:[https://www . geeksforgeeks . org/pyqt 5-背景-中间指示符图像复选框/](https://www.geeksforgeeks.org/pyqt5-background-image-of-intermediate-indicator-in-check-box/)

在这篇文章中，我们将看到如何设置背景图像的指标复选框时，它是在中间状态。默认情况下，复选框只有两种状态，尽管我们也可以设置第三种状态，该状态未被选中或未被选中，但借助`setTristate`方法，这两种状态之间的状态被称为中间状态。

为了给中间状态的指示器添加背景图像，我们必须更改中间状态指示器的样式表。下面是样式表代码。

```py
QCheckBox::indicator:indeterminate
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

        # setting tristate check box
        checkbox.setTristate(True)

        # changing size of indicator
        # adding background image to the indicator
        # when it is in intermediate state
        checkbox.setStyleSheet("QCheckBox::indicator"
                               "{"
                               "width : 60px;"
                               "height : 60px;"
                               "}"
                               "QCheckBox::indicator:indeterminate"
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

<video class="wp-video-shortcode" id="video-392121-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200330002433/Python-30-03-2020-00_22_10.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200330002433/Python-30-03-2020-00_22_10.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200330002433/Python-30-03-2020-00_22_10.mp4)</video>