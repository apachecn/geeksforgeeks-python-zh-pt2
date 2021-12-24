# pyqt 5–将背景图像从未选中的复选框

设置为按下的指示器

> 原文:[https://www . geesforgeks . org/pyqt 5-设置-背景-图像-按下-指示器-从-未选中-复选框/](https://www.geeksforgeeks.org/pyqt5-setting-background-image-to-pressed-indicator-from-unchecked-check-box/)

在本文中，我们将看到如何将背景图像添加到最初处于未选中状态的按下指示器中。为了做到这一点，我们必须改变与复选框对象相关联的样式表代码，并且当它被按下时，必须向未选中状态的指示器添加背景图像。

下面是样式表代码。

```py
QCheckBox::indicator:unchecked:pressed
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

        # changing size of indicator
        # adding background image to the indicator
        # when it is in unchecked state and when it get pressed
        checkbox.setStyleSheet("QCheckBox::indicator"
                               "{"
                               "width : 60px;"
                               "height : 60px;"
                               "}"
                               "QCheckBox::indicator:unchecked:pressed"
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

<video class="wp-video-shortcode" id="video-392055-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200329233528/Python-29-03-2020-23_33_44.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200329233528/Python-29-03-2020-23_33_44.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200329233528/Python-29-03-2020-23_33_44.mp4)</video>