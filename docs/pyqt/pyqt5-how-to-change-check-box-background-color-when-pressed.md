# pyqt 5–按下时如何更改复选框背景颜色

> 原文:[https://www . geesforgeks . org/pyqt 5-如何更改-复选框-背景色-按下时/](https://www.geeksforgeeks.org/pyqt5-how-to-change-check-box-background-color-when-pressed/)

在本文中，我们将了解如何在复选框被按下时为其设置背景色。默认情况下，没有与之关联的背景颜色。该背景颜色只有在复选框被按下时才会出现。

为了给复选框添加背景色，我们必须更改样式表代码，下面是这样做的样式表代码。

```
QCheckBox::pressed
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

        # creating the check-box
        checkbox1 = QCheckBox('Geek ?', self)

        # setting geometry of check box
        checkbox1.setGeometry(200, 150, 100, 40)

        # changing style sheet code of check box
        # adding background color to check box when it get pressed
        checkbox1.setStyleSheet("QCheckBox::pressed"
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

<video class="wp-video-shortcode" id="video-395431-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200403200411/Python-03-04-2020-20_03_52.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200403200411/Python-03-04-2020-20_03_52.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200403200411/Python-03-04-2020-20_03_52.mp4)</video>