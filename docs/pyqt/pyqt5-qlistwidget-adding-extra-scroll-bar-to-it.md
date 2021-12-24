# PyQt5 qlistwigt–向其添加额外滚动条

> 原文:[https://www . geeksforgeeks . org/pyqt5-qlistwigt-add-extra-滚动条-to-it/](https://www.geeksforgeeks.org/pyqt5-qlistwidget-adding-extra-scroll-bar-to-it/)

在本文中，我们将看到如何添加 QListWidget 的额外滚动条。QListWidget 是一个便利类，它提供了一个列表视图，带有一个经典的基于项目的界面，用于添加和删除项目。QListWidget 使用内部模型来管理列表中的每个 QListWidgetItem。将小部件作为滚动条小部件添加到对齐方式指定的位置。滚动条小部件显示在水平或垂直滚动条旁边，可以放在滚动条的两侧。如果希望滚动条小部件始终可见，请将相应滚动条的滚动条策略设置为始终打开。

> 为了做到这一点，我们将对列表小部件对象使用`addScrollBarWidget`方法。
> 
> **语法:**list _ widget . addscrollbarwidget(滚动条，对齐)
> 
> **参数:**它以 QScrollBar 和 QAlignment 对象作为参数
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

        # scroll bar
        scroll_bar = QScrollBar(self)

        # setting style sheet to the scroll bar
        scroll_bar.setStyleSheet("background : lightgreen;")

        # adding extra scroll bar to it
        list_widget.addScrollBarWidget(scroll_bar, Qt.AlignLeft)

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
![](img/c8e7006bad6943b7d8b29b85fdd8a42a.png)