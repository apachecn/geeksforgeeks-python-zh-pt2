# pyqt 5–鼠标悬停时如何将皮肤设置为选中的单选按钮指示器

> 原文:[https://www . geesforgeks . org/pyqt 5-如何设置选中皮肤-单选按钮-鼠标悬停时指示器/](https://www.geeksforgeeks.org/pyqt5-how-to-set-skin-to-checked-radiobutton-indicator-when-mouse-hover/)

在本文中，我们将看到当鼠标悬停在单选按钮上并处于选中状态时，如何将皮肤设置为单选按钮的指示器。默认情况下，没有皮肤或图像与之相关联，尽管我们可以设置皮肤。只有当指示器处于选中状态且鼠标悬停在单选按钮上时，皮肤才会出现。

为了给单选按钮的指示器添加皮肤，我们必须更改它的样式表代码。下面是样式表代码。

```py
QRadioButton::indicator:checked:hover
{
border-image : url(image.png);
}

```

下面是实现

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
        # setting skin to checked indicator when mouse hover it
        self.radio_button.setStyleSheet("QRadioButton::indicator:checked:hover"
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

<video class="wp-video-shortcode" id="video-396063-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200408020405/Python-08-04-2020-02_03_26.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200408020405/Python-08-04-2020-02_03_26.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200408020405/Python-08-04-2020-02_03_26.mp4)</video>