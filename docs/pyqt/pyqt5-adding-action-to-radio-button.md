# PyQt5–向单选按钮

添加动作

> 原文:[https://www . geesforgeks . org/pyqt 5-将动作添加到单选按钮/](https://www.geeksforgeeks.org/pyqt5-adding-action-to-radio-button/)

在本文中，我们将了解如何设置单选按钮的操作。将操作设置为单选按钮意味着向其添加一个操作，当单选按钮被选中或取消选中时，该操作将被调用并执行一些任务。

为了给单选按钮添加动作，我们将使用`toggled.connect`方法。

> **语法:**单选按钮。切换。连接(方法名)
> 
> **自变量:**以方法名为自变量。
> 
> **执行的动作:**当单选按钮被切换时，它将调用与之关联的方法。

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

        # creating a radio button
        self.radio_button = QRadioButton(self)

        # setting geometry of radio button
        self.radio_button.setGeometry(200, 150, 120, 40)

        # setting text to radio button
        self.radio_button.setText("GEEK ?")

        # creating label to display if it is checked or not
        self.label = QLabel("", self)

        # setting geometry of label
        self.label.setGeometry(200, 200, 150, 40)

        # adding action to radio button
        self.radio_button.toggled.connect(self.action)

    # method called by radio button
    def action(self):

        # changing the content of label
        self.label.setText("Action performed")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-393277-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200401002642/Python-01-04-2020-00_22_44.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200401002642/Python-01-04-2020-00_22_44.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200401002642/Python-01-04-2020-00_22_44.mp4)</video>