# PyQt5–按下时将背景颜色设置为不可编辑的组合框

> 原文:[https://www . geesforgeks . org/pyqt 5-设置-背景色-变为不可编辑-组合框-按下时/](https://www.geeksforgeeks.org/pyqt5-setting-background-color-to-non-editable-combobox-when-pressed/)

在本文中，我们将看到如何在按下不可编辑的组合框时为其设置背景色。只有当组合框处于不可编辑状态并被按下时，才会显示此背景色。

为此，我们必须更改组合框的样式表代码，下面是样式表代码

```py
QComboBox::!editable:pressed
{
background-color : lightgreen;
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

        # adding background color to the combo box when it is non editable
        # and when it get pressed
        self.combo_box.setStyleSheet("QComboBox::! editable:pressed"
                                     "{"
                                     "background-color: lightgreen;"
                                     "}")

        v = self.combo_box.view()
        # v.setStyleSheet("background : blue")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-398552-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200416193729/Python-16-04-2020-19_36_06.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200416193729/Python-16-04-2020-19_36_06.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200416193729/Python-16-04-2020-19_36_06.mp4)</video>