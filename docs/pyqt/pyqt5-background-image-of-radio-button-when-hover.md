# PyQt5–悬停时单选按钮的背景图像

> 原文:[https://www . geesforgeks . org/pyqt 5-背景-悬停时单选按钮图像/](https://www.geeksforgeeks.org/pyqt5-background-image-of-radio-button-when-hover/)

在本文中，我们将看到如何在鼠标(光标)悬停在单选按钮上时将背景图像设置为单选按钮，默认情况下没有图像设置。当鼠标悬停在单选按钮上时，将出现背景图像。

为此，我们必须更改样式表代码。下面是样式表代码。

```
QRadioButton::hover
{
background-image : url(image.png);
}

```

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
        self.radio_button.setText("Radio Button")

        # changing style sheet code of radio button
        # setting background image when mouse hover over it
        self.radio_button.setStyleSheet("QRadioButton::hover"
                                        "{"
                                        "background-image: url(image.png);"
                                        "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-394619-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200403020549/Python-03-04-2020-02_05_32.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200403020549/Python-03-04-2020-02_05_32.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200403020549/Python-03-04-2020-02_05_32.mp4)</video>