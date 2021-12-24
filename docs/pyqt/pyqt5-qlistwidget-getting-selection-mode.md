# PyQt5 qlistwigt–获取选择模式

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qlistwigt-get-selection-mode/](https://www.geeksforgeeks.org/pyqt5-qlistwidget-getting-selection-mode/)

在本文中，我们将看到如何将选择模式属性应用于 QListWidget。QListWidget 是一个便利类，它提供了一个列表视图，带有一个经典的基于项目的界面，用于添加和删除项目。QListWidget 使用内部模型来管理列表中的每个 QListWidgetItem。此属性保存视图在哪个选择模式下运行。此属性控制用户是否可以选择一个或多个项目，以及在多项目选择中，选择是否必须是连续的项目范围。可以借助`setSelectionMode`方法进行设置。

> 为了做到这一点，我们将对列表小部件对象使用`selectionMode`方法。
> 
> **语法:** list_widget.selectionMode()
> 
> **论证:**不需要论证
> 
> **返回:**返回选择模式对象，但打印时显示相关值

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

        # setting selection mode property
        list_widget.setSelectionMode(QAbstractItemView.MultiSelection)

        # creating a label
        label = QLabel("GeesforGeeks", self)

        # setting geometry to the label
        label.setGeometry(230, 80, 280, 80)

        # making label multi line
        label.setWordWrap(True)

        # getting selection mode property
        value = list_widget.selectionMode()

        # setting text to the label
        label.setText("Selection Mode : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/127c079256699e11ada20196570ba106.png)