# pyqt 5–更改单选按钮的颜色，使其处于选中状态

> 原文:[https://www . geeksforgeeks . org/pyqt 5-更改选中状态单选按钮的颜色/](https://www.geeksforgeeks.org/pyqt5-change-color-of-radio-button-for-checked-state/)

在本文中我们将看到如何改变单选按钮的颜色，当它处于选中状态时，默认情况下没有颜色设置为单选按钮的任何状态。为了将单选按钮的颜色设置为选中状态，我们必须更改单选按钮的选中状态的样式表。

下面是样式表代码。

```py
QRadioButton::checked
{
background-color : red;   
}

```

下面是实现。

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

        # changing style sheet code of radio button
        # setting background color for checked state
        self.radio_button.setStyleSheet("QRadioButton::checked"
                                        "{"
                                        "background-color : red;"
                                        "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-393327-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200403002955/Python-03-04-2020-00_28_16.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200403002955/Python-03-04-2020-00_28_16.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200403002955/Python-03-04-2020-00_28_16.mp4)</video>