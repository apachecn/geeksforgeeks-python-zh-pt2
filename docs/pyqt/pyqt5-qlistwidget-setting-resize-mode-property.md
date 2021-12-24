# PYqt5 QlisTwidget–设置调整大小模式属性

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qlistwigt-setting-resize-mode-property/](https://www.geeksforgeeks.org/pyqt5-qlistwidget-setting-resize-mode-property/)

在本文中，我们将看到如何将调整大小模式属性设置为 QListWidget。QListWidget 是一个便利类，它提供了一个列表视图，带有一个经典的基于项目的界面，用于添加和删除项目。QListWidget 使用内部模型来管理列表中的每个 QListWidgetItem。此属性保存视图调整大小时是否再次布局项目。如果此属性为“调整”，则在调整视图大小时，项目将再次布局。如果该值为“固定”，则在调整视图大小时，不会对项目进行布局。默认情况下，此属性设置为“固定”。

> 为了做到这一点，我们将对列表小部件对象使用`setResizeMode`方法。
> 
> **语法:** list_widget.setResizeMode(模式)
> 
> **参数:**以调整大小模式对象为参数
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

        # setting resize mode property
        list_widget.setResizeMode(QListView.Fixed)

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
![](img/e6cde78927985e92b9462b2a1f1f404b.png)