# pyqt 5–按下时将皮肤设置为中间复选框

> 原文:[https://www . geesforgeks . org/pyqt 5-设置-皮肤到中间-复选框-按下时/](https://www.geeksforgeeks.org/pyqt5-set-skin-to-intermediate-checkbox-when-pressed/)

在本文中，我们将看到如何设置皮肤复选框，当它已经处于中间(不确定)状态，当它被按下。默认情况下，没有与复选框关联的皮肤，皮肤基本上是背景图像，可以根据复选框的大小自行调整。

中间或不确定状态是复选框的第三种状态，可以借助`setTristate`方法添加。

为了在中间复选框被按下时给它添加皮肤，我们必须编辑样式表代码，下面是样式表代码。

```py
QCheckBox::indeterminate:pressed
{
border-image : url(image.png);
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
        checkbox1 = QCheckBox('Geek ?', self)

        # setting geometry of check box
        checkbox1.setGeometry(200, 150, 100, 40)

        # setting tri-state check box
        checkbox1.setTristate(True)

        # changing style sheet code of check box
        # adding skin to indeterminate check box when it get pressed
        checkbox1.setStyleSheet("QCheckBox::indeterminate:pressed"
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

<video class="wp-video-shortcode" id="video-395457-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200404013705/Python-04-04-2020-01_35_40.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200404013705/Python-04-04-2020-01_35_40.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200404013705/Python-04-04-2020-01_35_40.mp4)</video>