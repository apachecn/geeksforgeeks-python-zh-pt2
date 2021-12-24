# PyQt5–隐藏单选按钮

> 原文:[https://www . geesforgeks . org/pyqt 5-隐藏单选按钮/](https://www.geeksforgeeks.org/pyqt5-hiding-the-radio-button/)

在本文中，我们将看到如何隐藏单选按钮，当我们创建图形用户界面时，我们创建单选按钮，但是当它们的使用完成时，需要隐藏这些单选按钮，这样用户就不能再选中或取消选中它们了。

> **为了做到这一点，我们必须做到以下几点:**
> 
> 1.创建单选按钮
> 2。创建一个按钮
> 3。向单选按钮
> 4 添加动作。在动作内部，借助`setHidden`隐藏单选按钮

以下是实施–

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
        self.button = QPushButton("press to hide", self)

        # adding action to push button
        self.button.pressed.connect(self.change)

        # setting geometry to button
        self.button.setGeometry(100, 100, 100, 40)

    # method called by push button
    def change(self):

        # hiding the radio button
        self.radio_button.setHidden(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-395762-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200409231216/Python-09-04-2020-23_06_41.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200409231216/Python-09-04-2020-23_06_41.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200409231216/Python-09-04-2020-23_06_41.mp4)</video>