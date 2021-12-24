# pyqt 5–更改预先存在的单选按钮的文本

> 原文:[https://www . geeksforgeeks . org/pyqt 5-已有单选按钮的更改文本/](https://www.geeksforgeeks.org/pyqt5-change-text-of-pre-existing-radio-button/)

在本文中我们将看到如何在我们按下按钮时更改预先存在的单选按钮的文本，单选按钮文本可以借助`setText`方法进行更改。

> **为了做到这一点，我们必须做以下工作–**
> 
> 1.创建单选按钮
> 2。创建一个按钮
> 3。给按钮添加动作，这样当按钮被按下时，一个方法应该被称为
> 4。在方法内部，借助 setText 方法更改单选按钮的文本

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

        # creating push button
        self.button = QPushButton("press", self)

        # adding action to push button
        self.button.pressed.connect(self.change)

        # setting geometry to button
        self.button.setGeometry(200, 200, 100, 40)

    # method called by push button
    def change(self):

        # change the text of radio button
        self.radio_button.setText("Changed")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-395758-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200409025028/Python-09-04-2020-02_50_07.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200409025028/Python-09-04-2020-02_50_07.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200409025028/Python-09-04-2020-02_50_07.mp4)</video>