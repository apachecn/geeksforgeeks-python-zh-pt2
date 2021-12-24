# PyQt5 qlistwigt–设置交替行颜色属性

> 原文:[https://www . geeksforgeeks . org/pyqt5-qlistwigt-setting-alternating-row-color-property/](https://www.geeksforgeeks.org/pyqt5-qlistwidget-setting-alternating-row-color-property/)

在本文中，我们将看到如何设置 QListWidget 的交替行颜色属性。QListWidget 是一个便利类，它提供了一个列表视图，带有一个经典的基于项目的界面，用于添加和删除项目。QListWidget 使用内部模型来管理列表中的每个 QListWidgetItem。此属性决定是否使用交替颜色绘制背景。如果该属性为真，将使用 QPalette 绘制项目背景。基础和 QPalette。否则背景将使用 QPalette 绘制。基色。

> 为了做到这一点，我们将对列表小部件对象使用`setAlternatingRowColors`方法。
> 
> **语法:**list _ widget . setfilternatingowcolors(true)
> 
> **自变量:**它以布尔为自变量
> 
> **返回:**返回无

下面是实现

```py
# importing libraries
from PyQt5.QtWidgets import * 
from PyQt5 import QtCore, QtGui
from PyQt5.QtGui import * f
rom PyQt5.QtCore import * 
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
        item1 = QListWidgetItem("PyQt5 Geeks for Geeks")
        item2 = QListWidgetItem("B")
        item3 = QListWidgetItem("C")

        # adding items to the list widget
        list_widget.addItem(item1)
        list_widget.addItem(item2)
        list_widget.addItem(item3)

        # setting alternating row color property
        list_widget.setAlternatingRowColors(True)

        # setting word wrap property
        list_widget.setWordWrap(True)

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

<video class="wp-video-shortcode" id="video-464235-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200804000458/Python-2020-08-04-00-04-37.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200804000458/Python-2020-08-04-00-04-37.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200804000458/Python-2020-08-04-00-04-37.mp4)</video>