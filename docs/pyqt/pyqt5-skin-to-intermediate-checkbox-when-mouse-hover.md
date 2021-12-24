# pyqt 5–鼠标悬停时皮肤到中间复选框

> 原文:[https://www . geesforgeks . org/pyqt 5-鼠标悬停时皮肤到中间-复选框/](https://www.geeksforgeeks.org/pyqt5-skin-to-intermediate-checkbox-when-mouse-hover/)

在本文中，我们将看到如何设置皮肤复选框谁是在中间状态，鼠标悬停在它上面。默认情况下，没有图像与复选框相关联，此外观仅在鼠标悬停在复选框中间时出现。

中间(不确定)状态是介于选中和未选中状态之间的状态第三种状态，可以借助`setTristate`方法添加到复选框中。

为了设置外观，我们必须选中样式表代码的复选框，下面是样式表代码。

```
QCheckBox::indeterminate::hover
{
border-image : url(image.png);
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

        # setting tri-state check box
        checkbox1.setTristate(True)

        # changing style sheet code of check box
        # adding skin to indeterminate check box when mouse hover over it
        checkbox1.setStyleSheet("QCheckBox::indeterminate:hover"
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

<video class="wp-video-shortcode" id="video-395463-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200404195946/Python-04-04-2020-19_54_54.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200404195946/Python-04-04-2020-19_54_54.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200404195946/Python-04-04-2020-19_54_54.mp4)</video>