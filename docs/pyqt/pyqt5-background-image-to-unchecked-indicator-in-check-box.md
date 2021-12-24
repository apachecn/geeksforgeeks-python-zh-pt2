# pyqt 5–复选框

中未选中指示器的背景图像

> 原文:[https://www . geesforgeks . org/pyqt 5-背景-图像-未选中-复选框中的指示器/](https://www.geeksforgeeks.org/pyqt5-background-image-to-unchecked-indicator-in-check-box/)

在本文中，我们将看到如何设置背景图像为未选中复选框的指示器。默认情况下，指示器没有设置背景图像。

为了将背景图像设置为仅针对未选中状态的指示器，我们必须更改未选中状态指示器的样式表。下面是样式表代码。

```
QCheckBox::indicator:unchecked
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
        # creating the check-box
        checkbox = QCheckBox('Geek ?', self)

        # setting geometry of check box
        checkbox.setGeometry(200, 150, 100, 60)

        # changing size of indicator
        # adding background image to the indicator
        # when it is in unchecked state
        checkbox.setStyleSheet("QCheckBox::indicator"
                               "{"
                               "width : 60px;"
                               "height : 60px;"
                               "}"
                               "QCheckBox::indicator:unchecked"
                               "{"
                               "background-image : url(indicator_image.png);"
                               "width : 60px;"
                               "height : 60px;"
                               "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-392029-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200329231741/Python-29-03-2020-23_17_22.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200329231741/Python-29-03-2020-23_17_22.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200329231741/Python-29-03-2020-23_17_22.mp4)</video>