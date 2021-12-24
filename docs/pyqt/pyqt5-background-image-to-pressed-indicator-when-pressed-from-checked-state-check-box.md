# pyqt 5–从选中状态按下时按下指示器的背景图像|复选框

> 原文:[https://www . geesforgeks . org/pyqt 5-背景-图像-按下-指示器-按下时-从选中-状态-复选框/](https://www.geeksforgeeks.org/pyqt5-background-image-to-pressed-indicator-when-pressed-from-checked-state-check-box/)

在本文中，我们将看到如何将背景图像添加到最初处于选中状态的按下指示器中。为了做到这一点，我们必须改变与复选框对象相关联的样式表代码，并且必须在选中状态指示器被按下时向其添加背景图像。

下面是样式表代码。

```
QCheckBox::indicator:checked:pressed
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

        # changing size of indicator
        # adding background image to the pressed indicator
        # when it is in checked state
        checkbox.setStyleSheet("QCheckBox::indicator"
                               "{"
                               "width : 60px;"
                               "height : 60px;"
                               "}"
                               "QCheckBox::indicator:checked:pressed"
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

<video class="wp-video-shortcode" id="video-392061-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200329235623/Python-29-03-2020-23_54_32.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200329235623/Python-29-03-2020-23_54_32.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200329235623/Python-29-03-2020-23_54_32.mp4)</video>