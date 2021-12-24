# pyqt 5–鼠标悬停时单选按钮选中指示器的背景色

> 原文:[https://www . geesforgeks . org/pyqt 5-背景色-选中-鼠标悬停时单选按钮指示符/](https://www.geeksforgeeks.org/pyqt5-background-color-of-checked-indicator-of-radio-button-when-mouse-hover/)

在本文中，我们将看到当单选按钮处于选中状态并且鼠标悬停在其上时，我们如何设置它的背景色。默认情况下，没有与指示器相关联的颜色。

为了在指示器处于选中状态并且鼠标悬停在其上时为其添加背景色，我们必须更改单选按钮的样式表代码，下面是样式表代码。

```py
QRadioButton::indicator:checked:hover
{
background-color : lightgreen;
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
        # setting background color to checked indicator when mouse hover over it
        self.radio_button.setStyleSheet("QRadioButton::indicator:checked:hover"
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

<video class="wp-video-shortcode" id="video-395530-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200407025258/Python-07-04-2020-02_52_41.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200407025258/Python-07-04-2020-02_52_41.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200407025258/Python-07-04-2020-02_52_41.mp4)</video>