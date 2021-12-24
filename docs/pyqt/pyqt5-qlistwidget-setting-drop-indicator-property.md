# PYqt5 QlisTwidget–设置跌落指示器属性

> 原文:[https://www . geeksforgeeks . org/pyqt5-qlistwigt-setting-drop-indicator-property/](https://www.geeksforgeeks.org/pyqt5-qlistwidget-setting-drop-indicator-property/)

在本文中，我们将看到如何设置 QListWidget 的 drop indicator 属性。QListWidget 是一个便利类，它提供了一个列表视图，带有一个经典的基于项目的界面，用于添加和删除项目。QListWidget 使用内部模型来管理列表中的每个 QListWidgetItem。此属性保存启用拖放时显示的指示器，当我们将项目放在某个位置时，指示器会出现，并且可以随时关闭。

> 为了做到这一点，我们将对列表小部件对象使用`setDropIndicatorShown`方法。
> 
> **语法:**list _ widget . setdropdindicator shown(True)
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

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-463695-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200801010927/Python-2020-08-01-01-09-10.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200801010927/Python-2020-08-01-01-09-10.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200801010927/Python-2020-08-01-01-09-10.mp4)</video>