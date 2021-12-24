# PyQt5–在组合框

中给定的索引处添加项目

> 原文:[https://www . geesforgeks . org/pyqt 5-在给定索引中添加项目-组合框/](https://www.geeksforgeeks.org/pyqt5-adding-item-at-given-index-in-combobox/)

在本文中，我们将看到如何在给定索引的组合框中添加一个项目。我们知道我们可以借助`addItem`和`addItems`方法添加项目，但是项目只在末尾添加，为了在给定的索引处添加项目，我们使用`insertItem`方法。

> **语法:**组合框.插入项(索引，项)
> 
> **参数:**需要两个参数一个是整数即索引，第二个是字符串即项
> 
> **执行的操作:**它将在给定的索引处添加项目

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
        self.combo_box.setGeometry(200, 150, 120, 30)

        # geek list
        geek_list = ["Geek", "Geeky Geek", "Legend Geek", "Ultra Legend Geek"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # adding item at index 0
        self.combo_box.insertItem(0, "New ")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/5f7b1088da51e5cc153849beec2ad6e0.png)