# PyQt5–在组合框

中设置当前文本

> 原文:[https://www . geesforgeks . org/pyqt 5-setting-current-text-in-combobox/](https://www.geeksforgeeks.org/pyqt5-setting-current-text-in-combobox/)

在本文中，我们将看到如何借助其内容来选择项目。默认情况下，当我们创建一个组合框时，它会显示要选择的第一个项目，但是我们可以更改它，为了做到这一点，我们将使用`setCurrentText`方法。

> **语法:**组合框. setCurrentText(项)
> 
> **自变量:**以字符串为自变量
> 
> ***注意:*** 物品应该属于组合框物品列表
> 
> **执行的动作:**它将选择给定的项目

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

        # item
        item ="Legend Geek"

        # setting current item
        self.combo_box.setCurrentText(item)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/58cad8e9ebb0481b33172795a58d7bfe.png)