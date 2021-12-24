# PyQt5–鼠标悬停时不可编辑组合框的背景颜色

> 原文:[https://www . geesforgeks . org/pyqt 5-背景色-变为不可编辑-鼠标悬停时组合框/](https://www.geeksforgeeks.org/pyqt5-background-color-to-non-editable-combobox-when-mouse-hover/)

在本文中，我们将看到当鼠标悬停在不可编辑的组合框上时，我们如何设置它的背景颜色。只有当组合框处于不可编辑状态且鼠标悬停在其上时，才会显示此背景颜色。

为此，我们必须更改组合框的样式表代码，下面是样式表代码

```py
QComboBox::!editable:hover
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
        # and mouse hover over it
        self.combo_box.setStyleSheet("QComboBox::! editable:hover"
                                     "{"
                                     "background-color: lightgreen;"
                                     "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-398549-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200416192330/Python-16-04-2020-19_22_48.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200416192330/Python-16-04-2020-19_22_48.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200416192330/Python-16-04-2020-19_22_48.mp4)</video>