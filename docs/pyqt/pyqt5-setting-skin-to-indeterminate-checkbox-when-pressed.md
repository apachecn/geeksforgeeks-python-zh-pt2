# pyqt 5–按下时将皮肤设置为不确定复选框

> 原文:[https://www . geesforgeks . org/pyqt 5-设置-皮肤到不确定-复选框-按下时/](https://www.geeksforgeeks.org/pyqt5-setting-skin-to-indeterminate-checkbox-when-pressed/)

在本文中，我们将看到如何将皮肤设置为处于中间(不确定)状态并被按下的复选框的指示器，该皮肤仅在复选框被按下且其状态不确定时出现。不确定是复选框的第三种状态，介于选中和未选中状态之间，可以借助`setTristate`方法创建。

为了在复选框处于不确定状态并被按下时将 kin 添加到指示器中，我们必须更改样式表代码。下面是样式表代码。

```py
QCheckBox::indicator:indeterminate:pressed
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

        # setting tristate check box
        checkbox1.setTristate(True)
        # setting geometry of check box
        checkbox1.setGeometry(200, 150, 100, 40)

        # changing style sheet code of check box
        # adding skin to indeterminate indicator when it get pressed
        checkbox1.setStyleSheet("QCheckBox::indicator:indeterminate:pressed"
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

<video class="wp-video-shortcode" id="video-395475-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200405001116/Python-05-04-2020-00_10_49.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200405001116/Python-05-04-2020-00_10_49.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200405001116/Python-05-04-2020-00_10_49.mp4)</video>