# pyqt 5–单选按钮的选中指示器的背景颜色

> 原文:[https://www . geesforgeks . org/pyqt 5-背景色-待检查-单选按钮指示器/](https://www.geeksforgeeks.org/pyqt5-background-color-to-checked-indicator-of-radio-button/)

在本文中，我们将看到当单选按钮处于选中状态时，我们如何看到它的背景色。默认情况下，黑色圆圈与选中状态相关联，尽管我们可以用背景色来更改它。

为了给选中状态的指示器添加背景色，我们必须更改单选按钮的样式表，下面是样式表代码。

```
QRadioButton::indicator:checked
{
background-color : lightgreen;
}

```

下面是实现

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
        # setting background color to indicator when it is in checked state
        self.radio_button.setStyleSheet("QRadioButton::indicator:checked"
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

<video class="wp-video-shortcode" id="video-395525-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200407024312/Python-07-04-2020-02_42_57.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200407024312/Python-07-04-2020-02_42_57.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200407024312/Python-07-04-2020-02_42_57.mp4)</video>