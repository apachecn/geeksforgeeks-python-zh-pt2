# pyqt 5–将皮肤设置为单选按钮

的选中指示器

> 原文:[https://www . geeksforgeeks . org/pyqt 5-设置-皮肤待检查-无线电指示器按钮/](https://www.geeksforgeeks.org/pyqt5-setting-skin-to-checked-indicator-of-radiobutton/)

在本文中，我们将看到当单选按钮处于选中状态时，我们如何看到它的皮肤指示器。默认情况下，黑色圆圈与选中状态相关联，尽管我们可以为其添加皮肤。皮肤基本上是一个背景图像，它根据指示器的大小进行自我调整。此外观仅在单选按钮处于选中状态时出现。

为了做到这一点，我们必须改变单选按钮的样式表，下面是样式表代码。

```
QRadioButton::indicator:checked
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
        # setting skin to checked indicator
        self.radio_button.setStyleSheet("QRadioButton::indicator:checked"
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

<video class="wp-video-shortcode" id="video-396065-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200408021745/Python-08-04-2020-02_16_47.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200408021745/Python-08-04-2020-02_16_47.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200408021745/Python-08-04-2020-02_16_47.mp4)</video>