# PYqt5 QlisTwidget–获得选择行为

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qlistwigt-get-selection-behavior/](https://www.geeksforgeeks.org/pyqt5-qlistwidget-getting-selection-behaviour/)

在本文中，我们将看到如何获得 QListWidget 的选择行为。QListWidget 是一个便利类，它提供了一个列表视图，带有一个经典的基于项目的界面，用于添加和删除项目。QListWidget 使用内部模型来管理列表中的每个 QListWidgetItem。选择行为描述用户如何选择项目，可以是行，也可以是列，还可以是单个项目。可以借助`setSelectionBehavior`方法进行设置。

> 为了做到这一点，我们将对列表小部件对象使用`selectionBehavior`方法。
> 
> **语法:**list _ widget . selectionbehavior()
> 
> **论证:**不需要论证
> 
> **返回:**返回行为对象

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
        item1 = QListWidgetItem("PyQt5 Geeks for Geeks")
        item2 = QListWidgetItem("B")
        item3 = QListWidgetItem("C")

        # adding items to the list widget
        list_widget.addItem(item1)
        list_widget.addItem(item2)
        list_widget.addItem(item3)

        # setting selection behaviour
        list_widget.setSelectionBehavior(QAbstractItemView.SelectItems)

        # setting word wrap property
        list_widget.setWordWrap(True)

        # creating a label
        label = QLabel("GeesforGeeks", self)

        # setting geometry to the label
        label.setGeometry(230, 80, 280, 80)

        # making label multi line
        label.setWordWrap(True)

        # getting selection behaviour
        value = list_widget.selectionBehavior()

        # setting text to the label
        label.setText("Selection Behaviour : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/2f6e6fca72fee9e3aaf679b321fc13dc.png)