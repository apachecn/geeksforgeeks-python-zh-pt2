# PyQt5 qlistwigt–获取给定对齐方式下的所有滚动条

> 原文:[https://www . geeksforgeeks . org/pyqt5-qlistwigt-get-all-滚动条-at-给定-alignment/](https://www.geeksforgeeks.org/pyqt5-qlistwidget-getting-all-scroll-bar-at-given-alignment/)

在本文中，我们将看到如何在给定的对齐方式下获得 QListWidget 的滚动条。QListWidget 是一个便利类，它提供了一个列表视图，带有一个经典的基于项目的界面，用于添加和删除项目。QListWidget 使用内部模型来管理列表中的每个 QListWidgetItem。借助`addScrollBarWidget`方法，可以在特定的对齐方式下将滚动条添加到列表小部件中。

> 为了做到这一点，我们将对列表小部件对象使用`scrollBarWidgets`方法。
> 
> **语法:**list _ widget . scrollbarwidgets(对齐)
> 
> **自变量:**它以 QAlignment 对象为自变量
> 
> **返回:**返回 QScrollBar 小部件列表

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

        # getting scroll bar at right alignment
        value = list_widget.scrollBarWidgets(Qt.AlignRight)

        # setting text to the label
        label.setText(" Scroll Bar : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/e266de13af72b3874ff50fdd7e3855f6.png)