# pyqt 5–点击

设置未选中的复选框指示器背景颜色

> 原文:[https://www . geesforgeks . org/pyqt 5-设置-未选中-复选框-指示器-背景-颜色-点击/](https://www.geeksforgeeks.org/pyqt5-setting-unchecked-checkbox-indicator-background-color-on-click/)

在这篇文章中，我们将看到当我们在未选中状态下按下它时，如何为按下的指示器设置背景颜色。当按下它时，它的颜色应该会改变，并返回到选中状态的默认状态。

为此，我们必须更改与复选框对象一起使用的样式表代码。下面是样式表代码。

```
QCheckBox::indicator:unchecked:pressed
{
background-color : green;
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

        # adding background color to the indicator
        # when it is pressed from unchecked state
        checkbox.setStyleSheet("QCheckBox::indicator"
                               "{"
                               "width :30px;"
                               "height :30px;"
                               "}"
                               "QCheckBox::indicator:unchecked:pressed"
                               "{"
                               "background-color : green;"
                               "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-392023-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200329165443/Python-29-03-2020-16_53_13.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200329165443/Python-29-03-2020-16_53_13.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200329165443/Python-29-03-2020-16_53_13.mp4)</video>