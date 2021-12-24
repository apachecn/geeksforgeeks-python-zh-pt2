# PyQt5 qlistwigt–获取跌落指示器位置属性

> 原文:[https://www . geeksforgeeks . org/pyqt5-qlistwigt-get-drop-indicator-position-property/](https://www.geeksforgeeks.org/pyqt5-qlistwidget-getting-drop-indicator-position-property/)

在本文中，我们将看到如何获得 QListWidget 的放置指示器位置属性。QListWidget 是一个便利类，它提供了一个列表视图，带有一个经典的基于项目的界面，用于添加和删除项目。QListWidget 使用内部模型来管理列表中的每个 QListWidgetItem。此属性保存指示器位置，当启用拖放功能时会显示该位置，当我们将项目放在某个位置时，会出现一个指示器，它可以随时关闭。可以借助`setDropIndicatorShown`方法进行设置。位置可以在项目上、项目下或项目上，这取决于界面。

> 为了做到这一点，我们将对列表小部件对象使用`dropIndicatorPosition`方法。
> 
> **语法:**list _ widget . DropIndicator position()
> 
> **论证:**不需要论证
> 
> **返回:**它返回指示器位置对象，但打印时会显示与之相关的值

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
        item1 = QListWidgetItem("A")
        item2 = QListWidgetItem("B")
        item3 = QListWidgetItem("C")

        # adding items to the list widget
        list_widget.addItem(item1)
        list_widget.addItem(item2)
        list_widget.addItem(item3)

        # setting drag drop mode
        list_widget.setDragDropMode(QAbstractItemView.DragDrop)

        # making drop indicator enabled
        list_widget.setDropIndicatorShown(True)

        # creating a label
        label = QLabel("GeesforGeeks", self)

        # setting geometry to the label
        label.setGeometry(230, 80, 280, 80)

        # making label multi line
        label.setWordWrap(True)

        # getting drop indicator position property
        value = list_widget.dropIndicatorPosition()

        # setting text to the label
        label.setText("Drop Indicator Position : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/8b5701499e0669d9911b03280996c3b8.png)