# PYqt5 QlisTwidget–设置批量

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qlistwigt-setting-batch-size/](https://www.geeksforgeeks.org/pyqt5-qlistwidget-setting-batch-size/)

在本文中，我们将看到如何设置 QListWidget 的批处理大小。QListWidget 是一个便利类，它提供了一个列表视图，带有一个经典的基于项目的界面，用于添加和删除项目。QListWidget 使用内部模型来管理列表中的每个 QListWidgetItem。如果 layoutMode 设置为 Batched，此属性保存每个批处理中布局的项目数。默认值为 100，但可以随时更改。

> 为了做到这一点，我们将对列表小部件对象使用`setBatchSize`方法。
> 
> **语法:** list_widget.setBatchSize(n)
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

        # setting layout mode
        list_widget.setLayoutMode(QListView.Batched)

        # setting batch size
        list_widget.setBatchSize(20)

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
![](img/11cf2fa2ff97c6cd8b7e4eabdd952826.png)