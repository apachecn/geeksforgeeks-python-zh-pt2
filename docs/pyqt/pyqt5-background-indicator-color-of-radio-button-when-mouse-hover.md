# pyqt 5–鼠标悬停时单选按钮的背景指示灯颜色

> 原文:[https://www . geesforgeks . org/pyqt 5-背景-指示器-鼠标悬停时单选按钮的颜色/](https://www.geeksforgeeks.org/pyqt5-background-indicator-color-of-radio-button-when-mouse-hover/)

在本文中，我们将看到当鼠标悬停在单选按钮上时，我们如何设置它的背景色。默认情况下，当我们将鼠标悬停在单选按钮上时，没有颜色关联，尽管我们可以添加颜色。

为了改变鼠标悬停在指示器上时指示器的背景颜色，我们必须更改单选按钮的样式表代码，下面是样式表代码。

```
QRadioButton::indicator:hover
{
background-color : light green;
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
        # setting background color to indicator when mouse hover over it
        self.radio_button.setStyleSheet("QRadioButton::indicator:hover"
                                        "{"
                                        "background-color : lightgreen;"
                                        "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-395523-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200407023558/Python-07-04-2020-02_35_39.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200407023558/Python-07-04-2020-02_35_39.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200407023558/Python-07-04-2020-02_35_39.mp4)</video>