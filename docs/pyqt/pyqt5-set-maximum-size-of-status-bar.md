# PyQt5–设置状态栏的最大尺寸

> 原文:[https://www . geeksforgeeks . org/pyqt 5-set-最大大小状态栏/](https://www.geeksforgeeks.org/pyqt5-set-maximum-size-of-status-bar/)

我们知道默认情况下，当我们调整窗口大小时，状态栏也会调整大小。在本文中，我们将看到如何设置状态栏的最大大小，即当我们扩展窗口时，状态栏不应超过这个大小。

为了做到这一点，我们将使用带有状态栏对象的`setMaximumSize`方法。

> **语法:** self.statusBar()。设置最大尺寸(宽度、高度)
> 
> **自变量:**取两个自变量，都是整数，指的是宽度和高度。
> 
> **执行的操作:**将最大尺寸设置为状态栏。

**代码:**

```py
from PyQt5.QtCore import * 
from PyQt5.QtGui import * 
from PyQt5.QtWidgets import * 
import sys

class Window(QMainWindow):
    def __init__(self):
        super().__init__()

        # set the title
        self.setWindowTitle("Python")

        # setting  the geometry of window
        self.setGeometry(60, 60, 600, 400)

        # setting status bar message
        self.statusBar().showMessage("This is status bar")

        # setting  border and padding with different sizes
        self.statusBar().setStyleSheet("border :3px solid black;")

        # setting maximum size
        self.statusBar().setMaximumSize(400, 100)

        # creating a label widget
        self.label_1 = QLabel("status bar", self)

        # moving position
        self.label_1.move(100, 100)

        # setting up the border
        self.label_1.setStyleSheet("border :1px solid blue;")

        # resizing label
        self.label_1.adjustSize()

        # show all the widgets
        self.show()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/180b8299df7fd38f0089545f18172dec.png)