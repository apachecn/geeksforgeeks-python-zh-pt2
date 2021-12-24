# PYqt5 QlisTwidget–启用排序功能

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qlistwigt-making-sorting-enabled/](https://www.geeksforgeeks.org/pyqt5-qlistwidget-making-sorting-enabled/)

在本文中，我们将看到如何设置 QListWidget 的启用排序属性。QListWidget 是一个便利类，它提供了一个列表视图，带有一个经典的基于项目的界面，用于添加和删除项目。QListWidget 使用内部模型来管理列表中的每个 QListWidgetItem。此属性保存是否启用排序，如果此属性为真，则为列表启用排序，如果属性为假，则不启用排序。默认情况下，它是假的。

> 为了做到这一点，我们将对列表小部件对象使用`setSortingEnabled`方法。
> 
> **语法:**list _ widget . setsortingeabled(True)
> 
> **自变量:**它以布尔为自变量
> 
> **返回:**返回无

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
        self.setGeometry(100, 100, 500, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        # creating a QListWidget
        list_widget = QListWidget(self)

        # setting geometry to it
        list_widget.setGeometry(50, 70, 150, 60)

        # list widget items
        item1 = QListWidgetItem("A")
        item2 = QListWidgetItem("B")
        item3 = QListWidgetItem("C")

        # adding items to the list widget
        list_widget.addItem(item1)
        list_widget.addItem(item2)
        list_widget.addItem(item3)

        # setting sorting enabled
        list_widget.setSortingEnabled(True)

        # creating a label
        label = QLabel("GeesforGeeks", self)

        # setting geometry to the label
        label.setGeometry(230, 80, 300, 80)

        # making label multi line
        label.setWordWrap(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/7333f5d92cf6b1149ad61e4ff7663c3f.png)