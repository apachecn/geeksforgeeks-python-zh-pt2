# PyQt5 QDial–设置其下限

> 原文:[https://www . geesforgeks . org/pyqt 5-q dial-setting-it 下界/](https://www.geeksforgeeks.org/pyqt5-qdial-setting-lower-bound-of-it/)

在本文中，我们将看到如何设置 QDial 的下限。下限意味着 QDial 可以处理的最小值默认情况下，最小值是 0，尽管我们可以随时更改它。有了下界，我们就可以确定下界以下的数可以赋值。设置下限不会影响 Qdial 的移动，它仍然可以移动 360 度。

为此，我们对 QDial 对象使用`setMinimum`方法

> **语法:** dial.setMinimum(n)
> 
> **自变量:**以整数为自变量
> 
> **返回:**返回无

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
        self.setGeometry(100, 100, 500, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        # creating QDial object
        dial = QDial(self)

        # setting geometry to the dial
        dial.setGeometry(100, 100, 100, 100)

        # setting minimum value to the dial
        dial.setMinimum(50)

        # making notch visible
        dial.setNotchesVisible(True)

        # creating a label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry to the label
        label.setGeometry(220, 125, 200, 60)

        # making label multiline
        label.setWordWrap(True)

        # adding action to the dial
        dial.valueChanged.connect(lambda: label.setText("Value = " + str(dial.value())))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-446119-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200706025446/Python-2020-07-06-02-53-27.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200706025446/Python-2020-07-06-02-53-27.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200706025446/Python-2020-07-06-02-53-27.mp4)</video>