# pyqt 5–当单选按钮被按下时，为其指示器设置背景颜色

> 原文:[https://www . geesforgeks . org/pyqt 5-设置-背景色-单选按钮的指示器-按下时/](https://www.geeksforgeeks.org/pyqt5-setting-background-color-to-the-indicator-of-radio-button-when-it-get-pressed/)

在本文中，我们将了解如何在单选按钮被按下时为其指示器设置背景颜色，默认情况下，当我们按下单选按钮时会关联一种蓝色，尽管我们可以更改此颜色。

为了改变指示器被按下时的背景颜色，我们必须改变单选按钮的样式表代码，下面是样式表代码。

```py
QRadioButton::indicator:pressed
{
background-color : light green;
}

```

下面是实现。

```py
# importing libraries
from PyQt5.QtWidgets import * from PyQt5 import QtCore, QtGui
from PyQt5.QtGui import * from PyQt5.QtCore import * import sys

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
        # setting background color to indicator when it get pressed
        self.radio_button.setStyleSheet("QRadioButton::indicator:pressed"
                                        "{"
                                        "background-color : lightgreen;"
                                        "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-395521-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200407023208/Python-07-04-2020-02_31_25.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200407023208/Python-07-04-2020-02_31_25.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200407023208/Python-07-04-2020-02_31_25.mp4)</video>