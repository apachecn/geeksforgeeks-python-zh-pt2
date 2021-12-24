# PyQt5–更改单选按钮的状态

> 原文:[https://www . geesforgeks . org/pyqt 5-更改单选按钮状态/](https://www.geeksforgeeks.org/pyqt5-change-state-of-radio-button/)

在本文中，我们将看到如何改变单选按钮的状态。虽然借助`setChecked`方法我们可以使单选按钮被选中，但是当我们在选中的单选按钮上使用该方法时，单选按钮的状态将不会有任何变化。

> 为了在按下按钮时改变单选按钮的状态，我们必须执行以下操作–
> 
> 1.创建单选按钮
> 2。创建一个按钮
> 3。将一个方法连接到按钮，这样当按钮被按下时，方法被调用
> 4。在调用方法中借助`nextCheckState`方法改变单选按钮的状态。

下面是工具。

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
        self.radio_button = QRadioButton(self)

        # setting geometry of radio button
        self.radio_button.setGeometry(200, 150, 120, 40)

        # setting text to radio button
        self.radio_button.setText("Radio Button")

        # creating push button
        push = QPushButton("Press", self)

        # setting geometry of push button
        push.setGeometry(200, 200, 100, 40)

        # connect method to push button
        push.clicked.connect(self.method)

    def method(self):

        # changing the state of radio button
        self.radio_button.nextCheckState()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-393269-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200401201019/Python-01-04-2020-20_07_15.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200401201019/Python-01-04-2020-20_07_15.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200401201019/Python-01-04-2020-20_07_15.mp4)</video>