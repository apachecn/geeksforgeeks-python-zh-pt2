# PyQt5–复选框

中的图像

> 原文:[https://www.geeksforgeeks.org/pyqt5-image-in-check-box/](https://www.geeksforgeeks.org/pyqt5-image-in-check-box/)

在本文中，我们将看到如何设置背景图像复选框。当我们创建一个复选框时，虽然我们可以设置背景色，但没有与之相关的图像。下面是普通复选框和有图像复选框的图示。

![](img/d2dfcc641175982275e1636d32624e31.png) ![](img/14bdac8f4525ebd1b4fbe21e70780e58.png)

为了做到这一点，我们必须在样式表中设置背景图像，下面是可以与复选框对象一起使用的样式表代码。

```py
QCheckBox
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
        checkbox.setGeometry(200, 150, 100, 30)

        # setting stylesheet
        # adding background image to check box
        checkbox.setStyleSheet("QCheckBox"
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
![](img/aa1483d0b0ede144415440a297cea4e6.png)