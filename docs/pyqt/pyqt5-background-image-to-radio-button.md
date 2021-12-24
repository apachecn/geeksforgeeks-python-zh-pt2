# PyQt5–单选按钮的背景图像

> 原文:[https://www . geesforgeks . org/pyqt 5-背景-图像到单选按钮/](https://www.geeksforgeeks.org/pyqt5-background-image-to-radio-button/)

在本文中，我们将看到如何将背景图像设置为单选按钮，默认情况下没有与单选按钮相关联的图像，但是我们可以将背景图像添加到单选按钮的背景部分，单选按钮有两个部分一个是指示器，另一个是背景部分，即标签部分。

为了给单选按钮添加背景图像，我们必须更改单选按钮的样式表代码。下面是样式表代码。

```py
QRadioButton
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
        radio_button = QRadioButton(self)

        # setting geometry of radio button
        radio_button.setGeometry(200, 150, 120, 40)

        # setting text to radio button
        radio_button.setText("GEEK ?")

        # setting the style sheet
        # adding background image to the radio button
        radio_button.setStyleSheet("QRadioButton"
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
![](img/41c085b8315cde04f7bcca148c9d3359.png)