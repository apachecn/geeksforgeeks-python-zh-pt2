# PyQt5 QDial–滑块值改变信号

> 原文:[https://www . geesforgeks . org/pyqt 5-q dial-sliders-value-changed-signal/](https://www.geeksforgeeks.org/pyqt5-qdial-sliders-value-changed-signal/)

在这篇文章中，我们将看到如何获得滑块的值改变信号的 QDial。虽然我们可以通过`setValue`方法编程更改，但是用户可以通过鼠标来更改该值。当滑块值改变时，会发出此信号。

为此，我们对 QDial 对象使用`valueChanged`方法

> **语法:** dial.valueChanged.connect(方法)
> 
> **自变量:**以方法为自变量
> 
> **返回:**返回无

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

        # making notch visible
        dial.setNotchesVisible(True)

        # value
        value = 50

        # setting value to the dial slider
        dial.setValue(value)

        # creating a label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry to the label
        label.setGeometry(220, 125, 200, 60)

        # making label multiline
        label.setWordWrap(True)

        # getting slider value
        value = dial.value()

        # setting text to the label
        label.setText("Value : " + str(value))

        # getting value changed signal
        dial.valueChanged.connect(lambda: label.setText("Value = " + str(dial.value())))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-446133-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200706040015/Python-2020-07-06-03-59-52.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200706040015/Python-2020-07-06-03-59-52.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200706040015/Python-2020-07-06-03-59-52.mp4)</video>