# pyqt 5 qlist widget–getting layout mode

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qlistwigt-get-layout-mode/](https://www.geeksforgeeks.org/pyqt5-qlistwidget-getting-layout-mode/)

在本文中，我们将看到如何获得 QListWidget 的布局模式。QListWidget 是一个便利类，它提供了一个列表视图，带有一个经典的基于项目的界面，用于添加和删除项目。QListWidget 使用内部模型来管理列表中的每个 QListWidgetItem。此属性保存项目的布局模式。当模式为单遍(默认)时，项目会一次全部布局。当模式为批处理时，在处理事件时，项目以批处理大小的项目进行布局。这使得在布局其他项目时，可以立即查看可见项目并与之交互。可以借助`setLayoutMode`方法进行设置。

> 为了做到这一点，我们将对列表小部件对象使用`layoutMode`方法。
> 
> **语法:**list _ widget . layoutode(模式)
> 
> **论证:**不需要论证
> 
> **返回:**返回布局模式对象

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

        # setting layout mode
        list_widget.setLayoutMode(QListView.Batched)

        # creating a label
        label = QLabel("GeesforGeeks", self)

        # setting geometry to the label
        label.setGeometry(230, 80, 280, 80)

        # making label multi line
        label.setWordWrap(True)

        # getting layout mode
        value = list_widget.layoutMode()

        # setting text to the label
        label.setText("Layout Mode : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/fc0c791282b701b5c3c19aac1b847c49.png)