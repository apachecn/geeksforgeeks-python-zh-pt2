# pyqt 5–从中间状态按下时按下指示器的背景图像|复选框

> 原文:[https://www . geesforgeks . org/pyqt 5-背景-图像-按下-指示器-按下时-从中间状态-复选框/](https://www.geeksforgeeks.org/pyqt5-background-image-to-pressed-indicator-when-pressed-from-intermediate-state-check-box/)

在这篇文章中，我们将看到如何设置背景图像，当我们在中间状态下按下它时，按下指示器。当它被按下时，它的图像应该得到改变，并返回到其他状态的默认状态。默认情况下，复选框只有两种状态，虽然我们也可以设置第三种状态，这种状态没有被选中或取消选中，但是借助`setTristate`方法，这两种状态被称为中间状态。

为此，我们必须更改用于复选框对象的中间指示器的样式表代码。下面是样式表代码。

```
QCheckBox::indicator:indeterminate:pressed
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

        # setting tristate check box
        checkbox.setTristate(True)

        # changing size of indicator
        # adding background image to the pressed indicator
        # when it is in intermediate state
        checkbox.setStyleSheet("QCheckBox::indicator"
                               "{"
                               "width : 60px;"
                               "height : 60px;"
                               "}"
                               "QCheckBox::indicator:indeterminate::pressed"
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

<video class="wp-video-shortcode" id="video-392125-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200330003800/Python-30-03-2020-00_34_50.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200330003800/Python-30-03-2020-00_34_50.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200330003800/Python-30-03-2020-00_34_50.mp4)</video>