# PyQt5 qlistwigt–当前选定行信号

> 原文:[https://www . geeksforgeeks . org/pyqt5-qlistwigt-current-selected-row-signal/](https://www.geeksforgeeks.org/pyqt5-qlistwidget-current-selected-row-signal/)

在本文中，我们将看到如何获取 QListWidget 的当前选定行更改信号。QListWidget 是一个便利类，它提供了一个列表视图，带有一个经典的基于项目的界面，用于添加和删除项目。QListWidget 使用内部模型来管理列表中的每个 QListWidgetItem。当前行属性保存当前项的行。根据当前的选择模式，也可以借助`setCurrentRow`方法选择该行。只要当前项目发生变化，就会发出此信号。

> 为了做到这一点，我们将对列表小部件对象使用`currentRowChanged`方法。
> 
> **语法:**list _ widget . currentrowchanged . connect(方法)
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

        # setting current row
        list_widget.setCurrentRow(2)

        # creating a label
        label = QLabel("GeesforGeeks", self)

        # setting geometry to the label
        label.setGeometry(230, 80, 300, 80)

        # making label multi line
        label.setWordWrap(True)

        # getting row changed signal
        list_widget.currentRowChanged.connect(lambda: label.setText("Row Changed Signal"))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-462975-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200731002819/Python-2020-07-31-00-28-00.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200731002819/Python-2020-07-31-00-28-00.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200731002819/Python-2020-07-31-00-28-00.mp4)</video>