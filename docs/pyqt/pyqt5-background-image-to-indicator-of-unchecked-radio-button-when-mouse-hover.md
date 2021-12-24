# pyqt 5–鼠标悬停时未选中单选按钮指示器的背景图像

> 原文:[https://www . geesforgeks . org/pyqt 5-背景-图像-未选中指示器-鼠标悬停时单选按钮/](https://www.geeksforgeeks.org/pyqt5-background-image-to-indicator-of-unchecked-radio-button-when-mouse-hover/)

在本文中，我们将看到当鼠标悬停在单选按钮上并且处于未选中状态时，如何将背景图像设置为单选按钮的指示器。默认情况下，没有图像与之相关联，尽管我们可以向其添加图像。背景图像仅在指示器处于未选中状态以及鼠标悬停在单选按钮上时才会出现。

为了给单选按钮的指示器添加背景图像，我们必须更改它的样式表代码。下面是样式表代码。

```py
QRadioButton::indicator:unchecked:hover
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
        # setting background image unchecked indicator when mouse hover over it
        self.radio_button.setStyleSheet("QRadioButton::indicator:unchecked:hover"
                                        "{"
                                        "background-image : url(image.png);"
                                        "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-395737-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200408001853/Python-08-04-2020-00_16_41.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200408001853/Python-08-04-2020-00_16_41.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200408001853/Python-08-04-2020-00_16_41.mp4)</video>