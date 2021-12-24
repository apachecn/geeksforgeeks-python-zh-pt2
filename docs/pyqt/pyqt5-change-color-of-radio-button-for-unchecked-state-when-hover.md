# PyQt5–悬停时将单选按钮的颜色更改为未选中状态

> 原文:[https://www . geesforgeks . org/pyqt 5-更改单选按钮颜色-取消选中-悬停时的状态/](https://www.geeksforgeeks.org/pyqt5-change-color-of-radio-button-for-unchecked-state-when-hover/)

在本文中，我们将看到当单选按钮处于未选中状态并且鼠标悬停在其上时，我们如何更改它的颜色，默认情况下，没有颜色设置为任何状态，或者当鼠标悬停在单选按钮上时。

为了在未选中状态下将颜色设置为单选按钮，并将鼠标悬停在按钮上，我们必须更改未选中状态的样式表，当鼠标悬停在单选按钮上时，下面是样式表代码。

```py
QRadioButton::unchecked:hover
{
background-color : red;   
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
        # setting background color for unchecked state and mouse hover over
        self.radio_button.setStyleSheet("QRadioButton::unchecked:hover"
                                        "{"
                                        "background-color : red;"
                                        "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-394630-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200403003656/Python-03-04-2020-00_36_31.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200403003656/Python-03-04-2020-00_36_31.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200403003656/Python-03-04-2020-00_36_31.mp4)</video>