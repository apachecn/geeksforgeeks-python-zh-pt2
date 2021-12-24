# PyQt5 组合框–不同边框尺寸(厚度)的列表视图部分

> 原文:[https://www . geeksforgeeks . org/pyqt 5-组合框-列表-视图-带不同边框的零件-尺寸厚度/](https://www.geeksforgeeks.org/pyqt5-combo-box-list-view-part-with-different-border-sizethickness/)

在本文中，我们将看到如何为组合框列表视图的不同边创建不同的边框尺寸，即粗细。列表视图基本上是显示所有项目的组合框的一部分，下面是不同边框大小的组合框的外观

![](img/7c9b7c57c7355d4e69fbdb6e6142ba85.png)

为此，我们必须更改与组合框关联的样式表代码。以下是样式表代码–

```py
QListView
{
border : solid black;
border-width : 5px 5px 1px 1px;
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
        # creating a check-able combo box object
        self.combo_box = QComboBox(self)

        # setting geometry of combo box
        self.combo_box.setGeometry(200, 150, 150, 80)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # setting style sheet
        # adding different thickness border to list view
        self.combo_box.setStyleSheet("QListView"
                                     "{"
                                     "border : solid black;"
                                     "border-width : 5px 5px 1px 1px;"
                                     "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

window.show()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/74adeb1577cd82e002d8d6ecb2f43f0d.png)