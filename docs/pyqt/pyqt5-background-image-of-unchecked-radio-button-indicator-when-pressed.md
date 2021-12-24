# PyQt5–按下时未选中单选按钮指示器的背景图像

> 原文:[https://www . geesforgeks . org/pyqt 5-背景-未选中图像-单选按钮-按下时指示器/](https://www.geeksforgeeks.org/pyqt5-background-image-of-unchecked-radio-button-indicator-when-pressed/)

在这篇文章中，我们将看到我们如何设置背景图像的指示单选按钮时，它被按下，并在未经检查的状态。默认情况下，当我们按下单选按钮时，会有蓝色与之相关联，尽管我们可以更改它。背景图像只在指示器处于未选中状态和我们按下单选按钮时出现。

为了给单选按钮的指示器添加背景图像，我们必须更改它的样式表代码。下面是样式表代码。

```
QRadioButton::indicator:unchecked:pressed
{
background-image : url(image.png);
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
        # setting background image unchecked indicator when it get pressed
        self.radio_button.setStyleSheet("QRadioButton::indicator:unchecked:pressed"
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

<video class="wp-video-shortcode" id="video-395735-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200407234922/Python-07-04-2020-23_49_06.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200407234922/Python-07-04-2020-23_49_06.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200407234922/Python-07-04-2020-23_49_06.mp4)</video>