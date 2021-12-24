# PyQt5–设置组合框的背景颜色

> 原文:[https://www . geeksforgeeks . org/pyqt 5-设置-背景色-到-组合框/](https://www.geeksforgeeks.org/pyqt5-setting-background-color-to-the-combobox/)

在本文中，我们将看到如何设置组合框的背景颜色。默认情况下，组合框是灰色的，尽管我们可以更改它的颜色。下面是普通组合框和彩色组合框的表示。

![](img/0509c815e2a208730b525c27b681b2e0.png) ![](img/48c81e20f82c967cf0ca3a5c66731bc3.png)

为此，我们必须更改组合框的样式表代码，下面是样式表代码

```
QComboBox
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

        # creating a combo box widget
        self.combo_box = QComboBox(self)

        # setting geometry of combo box
        self.combo_box.setGeometry(200, 150, 150, 30)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # making it editable
        self.combo_box.setEditable(True)

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        self.combo_box.setStyleSheet("QComboBox"
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
![](img/8ea8da230be16d228458f15fa9142ec6.png)