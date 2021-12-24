# PYqt5 QlisTwidget–获取流量

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qlistwigt-get-its-flow/](https://www.geeksforgeeks.org/pyqt5-qlistwidget-getting-its-flow/)

在本文中，我们将看到如何获得 QListWidget 的流。QListWidget 是一个便利类，它提供了一个列表视图，带有一个经典的基于项目的界面，用于添加和删除项目。QListWidget 使用内部模型来管理列表中的每个 QListWidgetItem。流告诉列表小部件列表将如何，默认情况下列表是垂直的，即行，尽管通过改变流，我们也可以制作水平列表，但是可以借助`setFlow`方法来改变。

> 为了做到这一点，我们将对列表小部件对象使用`flow`方法。
> 
> **语法:** list_widget.flow()
> 
> **论证:**不需要论证
> 
> **返回:**返回流对象

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

        # setting flow
        list_widget.setFlow(QListView.LeftToRight)

        # creating a label
        label = QLabel("GeesforGeeks", self)

        # setting geometry to the label
        label.setGeometry(230, 80, 280, 80)

        # making label multi line
        label.setWordWrap(True)

        # getting flow property
        value = list_widget.flow()

        # setting text to the label
        label.setText("Flow : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/e4131f04aa5ab3e7bbe844d0fc7fb271.png)