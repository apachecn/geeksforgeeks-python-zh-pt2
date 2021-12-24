# pyqt 5–鼠标悬停时设置复选框指示器的外观

> 原文:[https://www . geesforgeks . org/pyqt 5-设置复选框皮肤-鼠标悬停时指示器/](https://www.geeksforgeeks.org/pyqt5-set-skin-of-checkbox-indicator-when-mouse-hover/)

在本文中，我们将看到当鼠标悬停在复选框上时，如何将皮肤设置为复选框的指示器。默认情况下，它们没有关联的皮肤/图像。只有当鼠标悬停在复选框上时，此外观才会出现。

为了在鼠标悬停在指示器上时给指示器添加皮肤，我们必须更改样式表代码。下面是样式表代码。

```
QCheckBox::indicator:hover
{
border-image : url(image.png)
}

```

下面是实现

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

        # setting tri-state check box
        checkbox1.setTristate(True)

        # changing style sheet code of check box
        # adding skin to indicator when it mouse hover over it
        checkbox1.setStyleSheet("QCheckBox::indicator:hover"
                                "{"
                                "border-image : url(image.png);"
                                "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-395469-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200404232613/Python-04-04-2020-23_24_27.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200404232613/Python-04-04-2020-23_24_27.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200404232613/Python-04-04-2020-23_24_27.mp4)</video>