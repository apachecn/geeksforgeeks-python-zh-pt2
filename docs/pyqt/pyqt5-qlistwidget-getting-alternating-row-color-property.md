# PyQt5 qlistwigt–获取交替行颜色属性

> 原文:[https://www . geeksforgeeks . org/pyqt5-qlistwigt-get-alternating-row-color-property/](https://www.geeksforgeeks.org/pyqt5-qlistwidget-getting-alternating-row-color-property/)

在本文中，我们将看到如何获得 QListWidget 的交替行颜色属性。QListWidget 是一个便利类，它提供了一个列表视图，带有一个经典的基于项目的界面，用于添加和删除项目。QListWidget 使用内部模型来管理列表中的每个 QListWidgetItem。此属性决定是否使用交替颜色绘制背景。如果该属性为真，将使用 QPalette 绘制项目背景。基础和 QPalette。否则背景将使用 QPalette 绘制。基色。可以借助`setAlternatingRowColors`方法进行设置。

> 为了做到这一点，我们将对列表小部件对象使用`alternatingRowColors`方法。
> 
> **语法:**list _ widget . alternatinglwcolors()
> 
> **论证:**不需要论证
> 
> **返回:**返回 bool

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

        # setting alternating row color property
        list_widget.setAlternatingRowColors(True)

        # setting word wrap property
        list_widget.setWordWrap(True)

        # creating a label
        label = QLabel("GeesforGeeks", self)

        # setting geometry to the label
        label.setGeometry(230, 80, 280, 80)

        # making label multi line
        label.setWordWrap(True)

        # getting alternate row color property
        value = list_widget.alternatingRowColors()

        # setting text to the label
        label.setText("Alternating Row Colors : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/5405db121d4c6fa439091237d4cb7e31.png)