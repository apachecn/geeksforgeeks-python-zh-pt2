# PyQt5–将皮肤设置为按下的单选按钮

> 原文:[https://www . geesforgeks . org/pyqt 5-设置皮肤按下单选按钮/](https://www.geeksforgeeks.org/pyqt5-set-skin-to-pressed-radio-button/)

在本文中，我们将看到如何设置皮肤按下单选按钮。默认情况下，没有图像/皮肤与单选按钮相关联，该皮肤只有在被按下时才会显示为复选框。

为了给按下的单选按钮添加皮肤，我们必须更改它的样式表代码，下面是样式表代码

```
QRadioButton::pressed
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
        # setting skin for pressed radio button
        self.radio_button.setStyleSheet("QRadioButton::pressed"
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

<video class="wp-video-shortcode" id="video-395511-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200405180617/Python-05-04-2020-18_04_48.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200405180617/Python-05-04-2020-18_04_48.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200405180617/Python-05-04-2020-18_04_48.mp4)</video>