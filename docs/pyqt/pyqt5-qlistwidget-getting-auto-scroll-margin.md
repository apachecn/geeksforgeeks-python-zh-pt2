# PyQt5 qlistwigt–获取自动滚动边距

> 原文:[https://www . geeksforgeeks . org/pyqt5-qlistwigt-get-auto-scroll-margin/](https://www.geeksforgeeks.org/pyqt5-qlistwidget-getting-auto-scroll-margin/)

在本文中，我们将看到如何获得 QListWidget 的自动滚动边距。QListWidget 是一个便利类，它提供了一个列表视图，带有一个经典的基于项目的界面，用于添加和删除项目。QListWidget 使用内部模型来管理列表中的每个 QListWidgetItem。当触发自动滚动时，此属性保存区域的大小。此属性控制触发自动滚动的视口边缘区域的大小。虽然可以借助`setAutoScrollMargin`方法更改，但默认值为 16 像素。

> 为了做到这一点，我们将对列表小部件对象使用`autoScrollMargin`方法。
> 
> **语法:**list _ widget . autoscrolmargin()
> 
> **论证:**不需要论证
> 
> **返回:**返回整数

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

        # setting drag and drop property
        list_widget.setDragDropMode(3)

        # setting auto scroll property
        list_widget.setAutoScroll(True)

        # setting auto scroll margin
        list_widget.setAutoScrollMargin(20)

        # setting word wrap property
        list_widget.setWordWrap(True)

        # creating a label
        label = QLabel("GeesforGeeks", self)

        # setting geometry to the label
        label.setGeometry(230, 80, 280, 80)

        # making label multi line
        label.setWordWrap(True)

        # getting auto scroll margin
        value = list_widget.autoScrollMargin()

        # setting text to the label
        label.setText("Auto Scroll Margin : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/b156844459f3ac6dbe8f9f96f1cc3ebb.png)