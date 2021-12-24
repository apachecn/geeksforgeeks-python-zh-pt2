# PyQt5 qlistwigt–获取自动滚动属性

> 原文:[https://www . geeksforgeeks . org/pyqt5-qlistwigt-get-auto-scroll-property/](https://www.geeksforgeeks.org/pyqt5-qlistwidget-getting-auto-scroll-property/)

在本文中，我们将看到如何获得 QListWidget 的自动滚动属性。QListWidget 是一个便利类，它提供了一个列表视图，带有一个经典的基于项目的界面，用于添加和删除项目。QListWidget 使用内部模型来管理列表中的每个 QListWidgetItem。此属性决定是否启用拖动移动事件中的自动滚动。如果此属性设置为 true(默认值)，则如果用户在视口边缘的 16 个像素范围内拖动，QAbstractItemView 会自动滚动视图的内容。如果当前项目发生变化，视图将自动滚动，以确保当前项目完全可见。可以借助`setAutoScroll`方法进行设置。

> 为了做到这一点，我们将对列表小部件对象使用`hasAutoScroll`方法。
> 
> **语法:** list_widget.hasAutoScroll()
> 
> **论证:**不需要论证
> 
> **返回:**返回 bool

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
        list_widget.setGeometry(50, 70, 150, 80)

        # list widget items
        item1 = QListWidgetItem("PyQt5 Geeks for Geeks")
        item2 = QListWidgetItem("B")
        item3 = QListWidgetItem("C")
        item4 = QListWidgetItem("D")

        # adding items to the list widget
        list_widget.addItem(item1)
        list_widget.addItem(item2)
        list_widget.addItem(item3)
        list_widget.addItem(item4)

        # setting drag and drop property
        list_widget.setDragDropMode(3)

        # setting auto scroll property
        list_widget.setAutoScroll(True)

        # setting word wrap property
        list_widget.setWordWrap(True)

        # creating a label
        label = QLabel("GeesforGeeks", self)

        # setting geometry to the label
        label.setGeometry(230, 80, 280, 80)

        # making label multi line
        label.setWordWrap(True)

        # getting auto scroll property property
        value = list_widget.hasAutoScroll()

        # setting text to the label
        label.setText("Has Auto Scroll : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/6a9aa05fbfa984e6256984447b2e2e5b.png)