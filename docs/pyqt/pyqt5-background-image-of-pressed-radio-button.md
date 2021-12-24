# pyqt 5–按下单选按钮的背景图像

> 原文:[https://www . geesforgeks . org/pyqt 5-背景-按下单选按钮的图像/](https://www.geeksforgeeks.org/pyqt5-background-image-of-pressed-radio-button/)

在这篇文章中，我们将看到如何设置背景图像到被按下的单选按钮，默认情况下，当单选按钮被按下时没有图像设置。选中或取消选中单选按钮时，每次都会出现按下的按钮背景图像。

为了给按下的单选按钮设置背景图像，我们必须更改样式表代码，下面是样式表代码。

```py
QRadioButton::pressed
{
background-image : url(image.png);
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
        # setting background image for pressed radio button
        self.radio_button.setStyleSheet("QRadioButton::pressed"
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

<video class="wp-video-shortcode" id="video-394617-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200403015950/Python-03-04-2020-01_58_33.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200403015950/Python-03-04-2020-01_58_33.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200403015950/Python-03-04-2020-01_58_33.mp4)</video>