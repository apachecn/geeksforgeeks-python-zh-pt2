# PYqt5 QlisTwidget–设置选择矩形可见属性

> 原文:[https://www . geeksforgeeks . org/pyqt5-qlistwigt-setting-selection-rectangle-visible-property/](https://www.geeksforgeeks.org/pyqt5-qlistwidget-setting-selection-rectangle-visible-property/)

在本文中，我们将看到如何设置 QListWidget 的选择矩形可见属性。QListWidget 是一个便利类，它提供了一个列表视图，带有一个经典的基于项目的界面，用于添加和删除项目。QListWidget 使用内部模型来管理列表中的每个 QListWidgetItem。如果该属性为真，则选择矩形可见；否则它将被隐藏。

**注意:**选择矩形只有在选择模式为可以选择多个项目的模式时才可见；也就是说，如果选择模式是 qabstraditemview . single selection，它将不会绘制选择矩形。

> 为了做到这一点，我们将对列表小部件对象使用`setSelectionRectVisible`方法。
> 
> **语法:**list _ widget . setselectionrectorvisible(True)
> 
> **自变量:**它以布尔为自变量
> 
> **返回:**返回无

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

        # setting selection mode property
        list_widget.setSelectionMode(QAbstractItemView.MultiSelection)

        # making selection rectangle visible
        list_widget.setSelectionRectVisible(True)

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

<video class="wp-video-shortcode" id="video-463729-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200803013700/Python-2020-08-03-01-36-41.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200803013700/Python-2020-08-03-01-36-41.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200803013700/Python-2020-08-03-01-36-41.mp4)</video>