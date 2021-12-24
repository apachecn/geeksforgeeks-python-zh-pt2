# pyqt 5–按下时将背景颜色设置为按下指示器

> 原文:[https://www . geesforgeks . org/pyqt 5-设置-背景色-按下-指示灯-按下时/](https://www.geeksforgeeks.org/pyqt5-setting-background-color-to-pressed-indicator-when-pressed/)

在本文中，我们将看到当我们在选中状态下按下时，如何为按下的指示器设置背景颜色。当它被按下时，它的颜色应该会改变，并返回到未选中状态的默认状态。

为了做到这一点，我们必须在指示器处于选中状态时更改指示器按下状态的样式表代码，它与复选框对象一起使用。下面是样式表代码。

```
QCheckBox::indicator:checked:pressed
{
background-color : red;
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
        checkbox.setGeometry(200, 150, 100, 30)

        # adding background color to the indicator
        # when it is pressed and in checked state
        checkbox.setStyleSheet("QCheckBox::indicator:checked:pressed"
                               "{"
                               "background-color : red;"
                               "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-392015-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200329193428/Python-29-03-2020-19_26_42.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200329193428/Python-29-03-2020-19_26_42.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200329193428/Python-29-03-2020-19_26_42.mp4)</video>