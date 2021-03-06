# PyQt5–按下时将边框添加到关闭状态组合框

> 原文:[https://www . geeksforgeeks . org/pyqt 5-添加边框到关闭状态-combobox-按下时/](https://www.geeksforgeeks.org/pyqt5-add-border-to-off-state-combobox-when-pressed/)

在本文中，我们将看到如何在组合框处于关闭状态并被按下时为其添加边框。关闭状态基本上是当组合框列表视图没有打开时。只有当组合框处于关闭状态并被按下时，此自定义边框才会出现。

为了做到这一点，我们必须更改与组合框关联的样式表，下面是样式表代码

```py
QComboBox::!on:pressed
{
border : 3px solid blue;
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

        # creating a combo box widget
        self.combo_box = QComboBox(self)

        # setting geometry of combo box
        self.combo_box.setGeometry(200, 150, 150, 30)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # editing style sheet code of combo box
        # adding border to the combo box when it is in off state
        # and when it get pressed
        self.combo_box.setStyleSheet("QComboBox::! on:pressed"
                                     "{"
                                     "border : 3px solid blue;"
                                     "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-399926-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200418030124/Python-18-04-2020-03_01_08.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200418030124/Python-18-04-2020-03_01_08.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200418030124/Python-18-04-2020-03_01_08.mp4)</video>