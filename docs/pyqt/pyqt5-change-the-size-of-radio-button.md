# PyQt5–更改单选按钮

的大小

> 原文:[https://www . geesforgeks . org/pyqt 5-更改单选按钮的大小/](https://www.geeksforgeeks.org/pyqt5-change-the-size-of-radio-button/)

在本文中我们将看到如何在我们按下按钮时改变预先存在的单选按钮的大小，我们可以借助`setGeometry`方法改变单选按钮的大小。

> **为了在按下按钮时改变单选按钮的大小，我们必须执行以下操作:**
> 
> 1.创建单选按钮
> 2。给单选按钮添加边框，这样我们就可以看到它的大小是否改变
> 3。创建按钮
> 4。向按钮添加动作，以便在按下按钮时调用方法
> 5。在侧面该方法借助`setGeometry`方法改变单选按钮的大小

以下是实施–

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
        # creating a radio button
        self.radio_button = QRadioButton("Radio button", self)

        # setting geometry of radio button
        self.radio_button.setGeometry(200, 150, 120, 40)

        # adding border to the radio button
        self.radio_button.setStyleSheet("border : 2px solid green;")

        # creating push button
        self.button = QPushButton("press", self)

        # adding action to push button
        self.button.pressed.connect(self.change)

        # setting geometry to button
        self.button.setGeometry(100, 100, 100, 40)

    # method called by push button
    def change(self):

        # change the size of radio button
        self.radio_button.setGeometry(200, 150, 200, 60)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-395760-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200409223609/Python-09-04-2020-22_33_02.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200409223609/Python-09-04-2020-22_33_02.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200409223609/Python-09-04-2020-22_33_02.mp4)</video>