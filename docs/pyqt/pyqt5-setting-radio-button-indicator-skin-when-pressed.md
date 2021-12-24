# PyQt5–按下时设置单选按钮指示器皮肤

> 原文:[https://www . geesforgeks . org/pyqt 5-设置-单选按钮-指示器-皮肤-按下时/](https://www.geeksforgeeks.org/pyqt5-setting-radio-button-indicator-skin-when-pressed/)

在这篇文章中，我们将看到如何设置皮肤的指示单选按钮时，它被按下。默认情况下，当指示器被按下时，蓝色会与指示器相关联，我们还可以为它设置皮肤。皮肤基本上是一个背景图像，它根据指示器的大小自行调整。

为了做到这一点，我们必须改变单选按钮的样式表，下面是样式表代码。

```py
QRadioButton::indicator:pressed
{
border-image : url(image.png);
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
        # setting skin to indicator when it get pressed
        self.radio_button.setStyleSheet("QRadioButton::indicator:pressed"
                                        "{"
                                        "border-image : url(image.png);"
                                        "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-396050-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200408013724/Python-08-04-2020-01_36_30.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200408013724/Python-08-04-2020-01_36_30.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200408013724/Python-08-04-2020-01_36_30.mp4)</video>