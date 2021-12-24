# PYqt 5–鼠标悬停在未选中的单选按钮上时，该按钮会变成皮肤

> 原文:[https://www . geesforgeks . org/pyqt 5-皮肤到未选中-鼠标悬停时单选按钮-it/](https://www.geeksforgeeks.org/pyqt5-skin-to-unchecked-radio-button-when-mouse-hover-it/)

在这篇文章中，我们将看到如何设置皮肤的单选按钮时，鼠标悬停在它上面，它是在未选中的状态，皮肤基本上是背景图像，它根据单选按钮的大小调整自己。只有当鼠标悬停在单选按钮上且处于未选中状态时，此外观才会出现。

为此，我们必须更改单选按钮的样式表代码，下面是样式表代码

```
QRadioButton::unchecked:hover
{
border-image : url(image.png);
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
        # setting skin for unchecked radio button when mouse hover over it
        self.radio_button.setStyleSheet("QRadioButton::unchecked:hover"
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

<video class="wp-video-shortcode" id="video-394673-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200405235616/Python-05-04-2020-23_55_34.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200405235616/Python-05-04-2020-23_55_34.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200405235616/Python-05-04-2020-23_55_34.mp4)</video>