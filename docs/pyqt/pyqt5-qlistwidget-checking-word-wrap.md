# pyqt 5 qlistwidget–检查文字环绕

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qlistwigt-checking-word-wrap/](https://www.geeksforgeeks.org/pyqt5-qlistwidget-checking-word-wrap/)

在本文中，我们将看到如何获得 QListWidget 的自动换行属性。QListWidget 是一个便利类，它提供了一个列表视图，带有一个经典的基于项目的界面，用于添加和删除项目。QListWidget 使用内部模型来管理列表中的每个 QListWidgetItem。此属性保存项目文本换行策略。如果此属性为真，则项目文本将在必要的地方换行；否则它根本不会被包装。该属性默认为假，可以借助`setWordWrap`方法进行设置。

> 为了做到这一点，我们将对列表小部件对象使用`wordWrap`方法。
> 
> **语法:**list _ widget . wordpwrap()
> 
> **论证:**不需要论证
> 
> **返回:**返回 bool

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
        item1 = QListWidgetItem("PyQt5 Geeks for Geeks")
        item2 = QListWidgetItem("B")
        item3 = QListWidgetItem("C")

        # adding items to the list widget
        list_widget.addItem(item1)
        list_widget.addItem(item2)
        list_widget.addItem(item3)

        # setting wordwrap property
        list_widget.setWordWrap(True)

        # creating a label
        label = QLabel("GeesforGeeks", self)

        # setting geometry to the label
        label.setGeometry(230, 80, 280, 80)

        # making label multi line
        label.setWordWrap(True)

        # getting word wrap property
        value = list_widget.wordWrap()

        # setting text to the label
        label.setText("Word Wrap  : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/f3671a3acc63d5c7a2bdced851f9e0d5.png)