# PyQt5–鼠标悬停在单选按钮上时，皮肤会变成单选按钮

> 原文:[https://www . geesforgeks . org/pyqt 5-鼠标悬停时皮肤到单选按钮/](https://www.geeksforgeeks.org/pyqt5-skin-to-radio-button-when-mouse-hover-over-it/)

在本文中，我们将看到如何在鼠标悬停在单选按钮上时为其设置皮肤，默认情况下，没有图像/皮肤与单选按钮相关联。皮肤是一个背景图像，可以根据单选按钮的大小自行调整。

为了在鼠标悬停在单选按钮上时为其添加皮肤，我们必须更改单选按钮的样式表代码，下面是样式表代码。

```
QRadioButton
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
        # setting skin for radio button when mouse hover over it
        self.radio_button.setStyleSheet("QRadioButton::hover"
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

<video class="wp-video-shortcode" id="video-394669-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200405192331/Python-05-04-2020-19_23_11.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200405192331/Python-05-04-2020-19_23_11.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200405192331/Python-05-04-2020-19_23_11.mp4)</video>