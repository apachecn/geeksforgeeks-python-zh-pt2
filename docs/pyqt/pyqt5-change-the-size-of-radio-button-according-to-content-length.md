# PyQt5–根据内容长度改变单选按钮的大小

> 原文:[https://www . geesforgeks . org/pyqt 5-根据内容长度更改单选按钮的大小/](https://www.geeksforgeeks.org/pyqt5-change-the-size-of-radio-button-according-to-content-length/)

在本文中，我们将看到如何根据单选按钮内部的内容来更改其大小。基本上，有两种方法可以做到这一点。首先是冗长的方法，我们得到单选按钮的内容，然后我们找到它的长度，然后根据长度改变单选按钮的大小，这是冗长的，不会那么准确，第二种方法是通过使用 adjustSize 方法，它会自动改变单选按钮的大小，并且更准确。

> **为了做到根据内容改变单选按钮大小我们要做到以下几点–**
> 1。创建单选按钮
> 2。创建一个按钮
> 3。向单选按钮
> 4 添加动作。在侧面动作中，使用调整方法
> 改变尺寸

下面是实现

## 蟒蛇 3

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
        # creating a radio button
        self.radio_button = QRadioButton("Radio button", self)

        # setting geometry of radio button
        self.radio_button.setGeometry(200, 150, 120, 40)

        # adding border to the radio button
        self.radio_button.setStyleSheet("border : 2px solid green;")

        # creating push button
        self.button = QPushButton("press to change", self)

        # adding action to push button
        self.button.pressed.connect(self.change)

        # setting geometry to button
        self.button.setGeometry(100, 100, 100, 40)

    # method called by push button
    def change(self):

        # adjusting the size of radio button
        self.radio_button.adjustSize()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-395753-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200409233334/Python-09-04-2020-23_28_02.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200409233334/Python-09-04-2020-23_28_02.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200409233334/Python-09-04-2020-23_28_02.mp4)</video>