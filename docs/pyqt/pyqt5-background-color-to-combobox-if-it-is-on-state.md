# PyQt5–如果组合框处于开启状态

则为背景色

> 原文:[https://www . geeksforgeeks . org/pyqt 5-背景色到组合框-如果是 on-state/](https://www.geeksforgeeks.org/pyqt5-background-color-to-combobox-if-it-is-on-state/)

在本文中，我们将看到如何在组合框处于打开状态时设置其背景颜色。默认情况下，组合框是灰色的，尽管我们可以更改它的颜色。此背景色仅在组合框小部件处于打开状态时出现。组合框的打开状态基本上是当下拉菜单打开时。

为此，我们必须更改组合框的样式表代码，下面是样式表代码

```py
QComboBox::on
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

        # adding background color to the combo box when it is in ON state
        self.combo_box.setStyleSheet("QComboBox::on"
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
![](img/2358e428c74282e2a64ce30e97a87bc7.png)
当我们打开下拉菜单
![](img/0e639789308f455af8f55f1847bdbf1c.png)