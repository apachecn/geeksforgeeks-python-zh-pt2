# pyqt 5–按下时单选按钮选中指示器的背景颜色

> 原文:[https://www . geeksforgeeks . org/pyqt 5-背景色-待检查-单选按钮指示器-按下时/](https://www.geeksforgeeks.org/pyqt5-background-color-to-checked-indicator-of-radio-button-when-pressed/)

在这篇文章中，我们将看到我们如何设置背景颜色的指示单选按钮，这是在检查状态，并得到按下。默认情况下，蓝色与此指示器相关联，尽管我们可以更改此颜色。

为了在指示器单选按钮处于选中状态并被按下时为其添加背景色，我们必须更改样式表代码。下面是样式表代码。

```py
QRadiobutton::indicator:checked:pressed
{
background-color : lightgreen;
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
        # setting background color to checked indicator when it get pressed
        self.radio_button.setStyleSheet("QRadioButton::indicator:checked:pressed"
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

<video class="wp-video-shortcode" id="video-395534-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200407031527/Python-07-04-2020-03_15_09.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200407031527/Python-07-04-2020-03_15_09.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200407031527/Python-07-04-2020-03_15_09.mp4)</video>