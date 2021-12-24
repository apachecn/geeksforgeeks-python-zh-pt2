# pyqt 5–按下时设置复选框指示器的皮肤

> 原文:[https://www . geesforgeks . org/pyqt 5-设置-复选框皮肤-按下时指示器/](https://www.geeksforgeeks.org/pyqt5-setting-skin-of-checkbox-indicator-when-pressed/)

在这篇文章中，我们将看到如何设置皮肤的指标时，复选框被按下。默认情况下，它们没有关联的皮肤/图像。只有当复选框被按下时，此皮肤才会出现。

为了在指示器被按下时增加外观，我们必须更改样式表代码。下面是样式表代码。

```py
QCheckBox::indicator::pressed
{
border-image : url(image.png)
}

```

下面是实现

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
        checkbox1 = QCheckBox('Geek ?', self)

        # setting geometry of check box
        checkbox1.setGeometry(200, 150, 100, 40)

        # setting tri-state check box
        checkbox1.setTristate(True)

        # changing style sheet code of check box
        # adding skin to indicator when it get pressed
        checkbox1.setStyleSheet("QCheckBox::indicator::pressed"
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

<video class="wp-video-shortcode" id="video-395467-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200404231745/Python-04-04-2020-23_16_19.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200404231745/Python-04-04-2020-23_16_19.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200404231745/Python-04-04-2020-23_16_19.mp4)</video>