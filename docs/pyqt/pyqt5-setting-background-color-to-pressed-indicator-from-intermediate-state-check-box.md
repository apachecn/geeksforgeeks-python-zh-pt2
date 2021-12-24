# pyqt 5–将背景颜色设置为从中间状态按下的指示器|复选框

> 原文:[https://www . geesforgeks . org/pyqt 5-设置-背景色-按下-指示器-从中间状态-复选框/](https://www.geeksforgeeks.org/pyqt5-setting-background-color-to-pressed-indicator-from-intermediate-state-check-box/)

在这篇文章中，我们将看到当我们在中间状态下按下指示器时，如何为按下的指示器设置背景颜色。当它被按下时，它的颜色应该会改变，并返回到其他状态的默认状态。默认情况下，复选框只有两种状态，尽管我们也可以使用第三种状态，即未选中或未选中的状态，借助`setTristate`方法，这两种状态之间的状态称为中间状态。

为此，我们必须更改用于复选框对象的中间指示器的样式表代码。下面是样式表代码。

```
QCheckBox::indicator:indeterminate:pressed
{
background-color : blue;
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

        # creating tri-state check box
        checkbox.setTristate(True)

        # adding background color to the pressed indicator
        # when it is in intermediate state
        checkbox.setStyleSheet("QCheckBox::indicator:indeterminate:pressed"
                               "{"
                               "background-color : blue;"
                               "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-392049-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200329202159/Python-29-03-2020-20_19_57.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200329202159/Python-29-03-2020-20_19_57.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200329202159/Python-29-03-2020-20_19_57.mp4)</video>