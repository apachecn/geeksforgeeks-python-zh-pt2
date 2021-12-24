# PYqt5 QlisTwidget–当前项目更改信号

> 原文:[https://www . geeksforgeeks . org/pyqt5-qlistwigt-current-item-changed-signal/](https://www.geeksforgeeks.org/pyqt5-qlistwidget-current-item-changed-signal/)

在本文中，我们将看到如何获得 QListWidget 的当前项目更改信号。QListWidget 是一个便利类，它提供了一个列表视图，带有一个经典的基于项目的界面，用于添加和删除项目。QListWidget 使用内部模型来管理列表中的每个 QListWidgetItem。当前项目可以从项目列表中设置。除非选择模式为“不选择”，否则项目也会被选择。可以借助`setCurrentItem`方法进行设置。当前项目更改时会发出此信号。

> 为了做到这一点，我们将对列表小部件对象使用`currentItemChanged`方法。
> 
> **语法:**list _ widget . current item changed . connect(方法)
> 
> **自变量:**以方法为自变量
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

        # setting current item
        list_widget.setCurrentItem(item2)

        # creating a label
        label = QLabel("GeesforGeeks", self)

        # setting geometry to the label
        label.setGeometry(230, 80, 280, 80)

        # making label multi line
        label.setWordWrap(True)

        # getting item changed signal
        list_widget.currentItemChanged.connect(lambda: label.setText("Item Changed Signal"))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-462977-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200731010645/Python-2020-07-31-01-06-25.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200731010645/Python-2020-07-31-01-06-25.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200731010645/Python-2020-07-31-01-06-25.mp4)</video>