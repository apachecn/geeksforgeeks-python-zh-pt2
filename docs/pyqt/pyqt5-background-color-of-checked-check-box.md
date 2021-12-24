# PyQt5–选中复选框

的背景颜色

> 原文:[https://www . geesforgeks . org/pyqt 5-背景色-选中-复选框/](https://www.geeksforgeeks.org/pyqt5-background-color-of-checked-check-box/)

在本文中，我们将看到如何设置复选框的颜色，即当复选框处于选中状态时，设置标签部分的颜色。我们可以将背景颜色设置为复选框，但所有州的背景颜色将保持不变。

为了设置选中状态的背景颜色，我们必须在选中状态下更改标签部分的样式表。下面是样式表代码。

```
QCheckBox::checked
{
background-color : pink;
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
        # creating the check-box
        checkbox = QCheckBox('Geek ?', self)

        # setting geometry of check box
        checkbox.setGeometry(200, 150, 100, 30)

        # adding background color to the check box label part
        # when it is in checked state
        checkbox.setStyleSheet("QCheckBox::checked"
                               "{"
                               "background-color : pink;"
                               "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-392133-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200330022158/Python-30-03-2020-02_20_49.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200330022158/Python-30-03-2020-02_20_49.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200330022158/Python-30-03-2020-02_20_49.mp4)</video>