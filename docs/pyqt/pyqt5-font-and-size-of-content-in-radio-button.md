# PyQt5–单选按钮

中内容的字体和大小

> 原文:[https://www . geeksforgeeks . org/pyqt 5-单选按钮中内容的字体和大小/](https://www.geeksforgeeks.org/pyqt5-font-and-size-of-content-in-radio-button/)

在本文中，我们将看到如何为单选按钮的内容设置字体和大小，单选按钮基本上有两个部分，一个是指示器部分，另一个是包含内容的标签部分。

为了改变字体和内容的大小，我们必须改变单选按钮的样式表代码，下面是样式表代码

```
QRadioButton
{
font : 20px Ariral;
}

```

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
        self.button = QPushButton("press to change", self)

        # adding action to push button
        self.button.pressed.connect(self.change)

        # setting geometry to button
        self.button.setGeometry(100, 100, 100, 40)

    # method called by push button
    def change(self):

        # setting font to the style sheet
        self.radio_button.setStyleSheet("QRadioButton"
                                        "{"
                                        "font : 20px Arial;"
                                        "}")

        # adjusting the size
        self.radio_button.adjustSize()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-395764-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200410000334/Python-10-04-2020-00_02_52.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200410000334/Python-10-04-2020-00_02_52.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200410000334/Python-10-04-2020-00_02_52.mp4)</video>