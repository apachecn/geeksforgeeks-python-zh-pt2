# pyqt 5–按下的单选按钮的背景颜色

> 原文:[https://www . geesforgeks . org/pyqt 5-背景色-按下单选按钮/](https://www.geeksforgeeks.org/pyqt5-background-color-of-pressed-radio-button/)

在本文中，我们将看到如何为按下的单选按钮设置颜色，默认情况下，当单选按钮被按下时，没有颜色设置。每次选中或取消选中单选按钮时，按下的按钮颜色都会出现。

为了给按下的单选按钮设置背景颜色，我们必须更改样式表代码，下面是样式表代码。

```
QRadioButton::pressed
{
background-color : red;
}

```

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
        # setting background color for pressed radio button
        self.radio_button.setStyleSheet("QRadioButton::pressed"
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

<video class="wp-video-shortcode" id="video-394615-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200403015146/Python-03-04-2020-01_51_27.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200403015146/Python-03-04-2020-01_51_27.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200403015146/Python-03-04-2020-01_51_27.mp4)</video>