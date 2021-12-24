# pyqt 5–设置组合框中项目数量的限制

> 原文:[https://www . geeksforgeeks . org/pyqt 5-设置组合框中项目数量的限制/](https://www.geeksforgeeks.org/pyqt5-setting-limit-to-number-of-items-in-combobox/)

在本文中，我们将看到如何限制组合框中的项目数量。当我们创建一个组合框时，没有对项目设置限制，我们可以添加任意数量的项目，尽管有时会出现对项目设置最大限制的情况。

为了设置物品数量的最大限制，我们使用`setMaxCount`方法。

> **语法:**组合框. setMaxCount(n)
> 
> **自变量:**以整数为自变量
> 
> **执行的操作:**这将设置组合框中项目数量的最大限制

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
        self.combo_box.setGeometry(200, 150, 120, 30)

        # geek list
        geek_list = ["Geek", "Geeky Geek", "Legend Geek", "Ultra Legend Geek"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # setting maximum number limit of items
        self.combo_box.setMaxCount(2)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/9dc04527a1e20361ae5767ee474e623c.png)