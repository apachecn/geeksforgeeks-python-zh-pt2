# PyQt5–鼠标悬停时将背景颜色设置为组合框

> 原文:[https://www . geesforgeks . org/pyqt 5-设置-背景-颜色-鼠标悬停时组合框/](https://www.geeksforgeeks.org/pyqt5-setting-background-color-to-combobox-when-mouse-hover/)

在本文中，我们将看到当鼠标悬停在组合框上时，如何设置组合框的背景颜色。默认情况下，组合框是灰色的，尽管我们可以更改它的颜色。此背景色仅在鼠标悬停在组合框小部件上时出现。

为此，我们必须更改组合框的样式表代码，下面是样式表代码–

```
QComboBox::hover
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

        # adding background color to the combo box when mouse hover over it
        self.combo_box.setStyleSheet("QComboBox::hover"
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
![](img/227d2226ddbb6f5a68c093f9db19fbe6.png)
当鼠标悬停在组合框上时，它看起来像这样
![](img/aea8a839c83759bb3f02077cf8938cfc.png)