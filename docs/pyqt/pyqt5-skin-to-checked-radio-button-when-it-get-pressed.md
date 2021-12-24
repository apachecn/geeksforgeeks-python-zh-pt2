# pyqt 5–按下单选按钮时皮肤被选中

> 原文:[https://www . geesforgeks . org/pyqt 5-皮肤待检查-单选按钮-按下时/](https://www.geeksforgeeks.org/pyqt5-skin-to-checked-radio-button-when-it-get-pressed/)

在这篇文章中，我们将看到如何设置皮肤的单选按钮，当它被按下并处于选中状态，皮肤基本上是背景图像，它根据单选按钮的大小进行自我调整。只有当单选按钮被按下并且已经处于选中状态时，此外观才会出现。

为此，我们必须更改单选按钮的样式表代码，下面是样式表代码

```
QRadioButton::checked::pressed
{
border-image : url(image.png);
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
        # setting skin for checked radio button when it get pressed
        self.radio_button.setStyleSheet("QRadioButton::checked:pressed"
                                        "{"
                                        "border-image: url(image.png);"
                                        "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-394671-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200405233555/Python-05-04-2020-23_35_33.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200405233555/Python-05-04-2020-23_35_33.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200405233555/Python-05-04-2020-23_35_33.mp4)</video>