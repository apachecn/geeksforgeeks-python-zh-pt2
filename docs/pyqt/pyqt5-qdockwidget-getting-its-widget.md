# PyQt5 QDockWidget–获取其小部件

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdock widget-get-its-widget/](https://www.geeksforgeeks.org/pyqt5-qdockwidget-getting-its-widget/)

在本文中，我们将看到如何获得 QDockWidget 的小部件。QDockWidget 提供了 dock widgets 的概念，也称为工具选项板或实用程序窗口。停靠窗口是放置在 QMainWindow(原始窗口)中央小部件周围的停靠小部件区域中的辅助窗口。
我们可以借助`setWidget`方法将 widget 添加到 dock widget 中，widget 可以是任意的 widget，甚至是包含多个小子 widget 的单个 widget。除了 dock 小部件，为其设置的小部件也会随之移动。默认情况下，没有小部件被设置到 dock。

> 为此，我们将对 dock widget 对象使用`widget`方法。
> 
> **语法:** dock.widget()
> 
> **论证:**不需要论证
> 
> **返回:**返回 QWidget

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

        # creating dock widget
        dock = QDockWidget("GeeksforGeeks", self)

        # push button
        push = QPushButton("Press", self)

        # setting widget to the dock
        dock.setWidget(push)

        # setting geometry tot he dock widget
        dock.setGeometry(100, 0, 200, 30)

        # creating a label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 80)

        # making label multi line
        label.setWordWrap(True)

        # getting widget of the dock
        value = dock.widget()

        # setting text to the label
        label.setText("Widget : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/355beae1337d8c167f683504d3972f22.png)