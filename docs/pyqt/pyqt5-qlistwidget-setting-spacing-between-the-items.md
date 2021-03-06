# PyQt5 qlistwigt–设置项目之间的间距

> 原文:[https://www . geeksforgeeks . org/pyqt5-qlistwigt-setting-项目间距/](https://www.geeksforgeeks.org/pyqt5-qlistwidget-setting-spacing-between-the-items/)

在本文中，我们将看到如何设置 QListWidget 的项目之间的空间。QListWidget 是一个便利类，它提供了一个列表视图，带有一个经典的基于项目的界面，用于添加和删除项目。QListWidget 使用内部模型来管理列表中的每个 QListWidgetItem。Spacing 属性保存布局中项目周围的空间。此属性是布局中项目周围填充的空白空间的大小。当视图可见时设置此属性将导致项目再次布局。默认情况下，此属性包含值 0。

> 为了做到这一点，我们将对列表小部件对象使用`setSpacing`方法。
> 
> **语法:** list_widget.setSpacing(n)
> 
> **自变量:**以整数为自变量
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

        # setting spacing property
        list_widget.setSpacing(5)

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

<video class="wp-video-shortcode" id="video-463733-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200803015233/Python-2020-08-03-01-52-14.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200803015233/Python-2020-08-03-01-52-14.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200803015233/Python-2020-08-03-01-52-14.mp4)</video>