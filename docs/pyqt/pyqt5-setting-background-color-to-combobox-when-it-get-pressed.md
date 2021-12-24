# PyQt5–按下组合框时设置背景颜色

> 原文:[https://www . geesforgeks . org/pyqt 5-设置-背景-颜色到组合框-按下时/](https://www.geeksforgeeks.org/pyqt5-setting-background-color-to-combobox-when-it-get-pressed/)

在本文中，我们将看到如何在组合框被按下时为其设置背景色。默认情况下，组合框是灰色的，尽管我们可以更改它的颜色。此背景色仅在组合框小部件被按下时出现。

为此，我们必须更改组合框的样式表代码，下面是样式表代码

```py
QComboBox::pressed
{
background-color : lightgreen;
}

```

以下是实施–

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

        # making it editable
        self.combo_box.setEditable(True)

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # adding background color to the combo box when it get pressed
        self.combo_box.setStyleSheet("QComboBox::pressed"
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
按下时看起来是这样的
![](img/97614b923b1f53b255ad6d23b8cdcbbb.png)