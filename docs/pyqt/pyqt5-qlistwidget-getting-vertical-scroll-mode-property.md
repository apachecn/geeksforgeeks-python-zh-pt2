# PyQt5 qlistwigt–获取垂直滚动模式属性

> 原文:[https://www . geeksforgeeks . org/pyqt5-qlistwigt-get-vertical-scroll-mode-property/](https://www.geeksforgeeks.org/pyqt5-qlistwidget-getting-vertical-scroll-mode-property/)

在本文中，我们将看到如何获得 QListWidget 的垂直滚动模式属性。QListWidget 是一个便利类，它提供了一个列表视图，带有一个经典的基于项目的界面，用于添加和删除项目。QListWidget 使用内部模型来管理列表中的每个 QListWidgetItem。此属性控制视图如何垂直滚动其内容。滚动可以按像素或按项目进行。它的默认值来自通过 QStyle 的样式。SH_ItemView_ScrollMode 样式提示。可以借助`setVerticalScrollMode`方法进行设置。

> 为了做到这一点，我们将对列表小部件对象使用`verticalScrollMode`方法。
> 
> **语法:**list _ widget . verticalscrollmode()
> 
> **论证:**不需要论证
> 
> **返回:**返回滚动模式对象

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

        # setting vertical scroll mode
        list_widget.setVerticalScrollMode(QAbstractItemView.ScrollPerPixel)

        # resetting horizontal scroll mode
        list_widget.resetHorizontalScrollMode()

        # creating a label
        label = QLabel("GeesforGeeks", self)

        # setting geometry to the label
        label.setGeometry(230, 80, 280, 80)

        # making label multi line
        label.setWordWrap(True)

        # getting vertical scroll mode property
        value = list_widget.verticalScrollMode()

        # setting text to the label
        label.setText("Vertical Scroll Mode : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/a5bcbf4e2be6bd8da2e5f93c32fec16c.png)