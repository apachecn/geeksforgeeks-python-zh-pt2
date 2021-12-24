# PyQt5–如何停止单选按钮被选中

> 原文:[https://www . geeksforgeeks . org/pyqt 5-如何停止单选按钮-免于被检查/](https://www.geeksforgeeks.org/pyqt5-how-to-stop-radio-button-from-getting-checked/)

在本文中，我们将看到如何停止单选按钮进行检查，有时需要阻止单选按钮，这样用户就无法检查它。

为了阻止单选按钮被选中，我们必须更改单选按钮的可检查属性，并将其设置为 False。

> **语法:**单选按钮。设置可检查(假)
> 
> **自变量:**它以布尔为自变量
> 
> **动作:**不允许按钮被勾选。

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

        # changing check-able property of radio button
        self.radio_button.setCheckable(False)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-393265-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200401225453/Python-01-04-2020-22_54_11.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200401225453/Python-01-04-2020-22_54_11.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200401225453/Python-01-04-2020-22_54_11.mp4)</video>