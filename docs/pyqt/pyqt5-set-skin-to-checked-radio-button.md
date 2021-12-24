# PyQt5–将皮肤设置为选中单选按钮

> 原文:[https://www . geesforgeks . org/pyqt 5-设置皮肤检查单选按钮/](https://www.geeksforgeeks.org/pyqt5-set-skin-to-checked-radio-button/)

在本文中，我们将看到如何将皮肤设置为选中复选框，默认情况下，没有与单选按钮相关联的图像/皮肤，当单选按钮处于选中状态时，将出现此皮肤。

为了给选中状态的单选按钮添加外观，我们必须更改单选按钮的样式表。下面是样式表代码。

```
QRadioButton::checked
{
background-image : url(image.png);
}

```

下面是实现。

```
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
        # setting skin for checked radio button
        self.radio_button.setStyleSheet("QRadioButton::checked"
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

<video class="wp-video-shortcode" id="video-395517-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200406001023/Python-06-04-2020-00_09_57.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200406001023/Python-06-04-2020-00_09_57.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200406001023/Python-06-04-2020-00_09_57.mp4)</video>