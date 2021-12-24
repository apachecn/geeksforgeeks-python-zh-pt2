# pyqt 5–悬停时单选按钮处于选中状态的背景图像

> 原文:[https://www . geeksforgeeks . org/pyqt 5-悬停时选中状态单选按钮的背景图像/](https://www.geeksforgeeks.org/pyqt5-background-image-of-radio-button-for-checked-state-when-hover/)

在这篇文章中，我们将看到如何设置背景图像为单选按钮，当它处于选中状态并且鼠标悬停在它上面时，默认情况下没有图像设置为任何状态或者当鼠标悬停在单选按钮上面时。

为了将背景图像设置为选中状态的单选按钮，并将鼠标悬停在其上，我们必须更改选中状态的样式表，当鼠标悬停在单选按钮上时，下面是样式表代码。

```py
QRadioButton::checked:hover
{
background-image : url(image.png);   
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
        # setting background image for checked state and mouse hover over
        self.radio_button.setStyleSheet("QRadioButton::checked:hover"
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

<video class="wp-video-shortcode" id="video-394607-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200403012800/Python-03-04-2020-01_27_42.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200403012800/Python-03-04-2020-01_27_42.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200403012800/Python-03-04-2020-01_27_42.mp4)</video>