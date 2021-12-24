# PyQt5–设置状态栏的固定大小

> 原文:[https://www . geesforgeks . org/pyqt 5-set-fixed-size-of-status bar/](https://www.geeksforgeeks.org/pyqt5-set-fixed-size-of-statusbar/)

在 PyQt5 中，当我们创建一个状态栏时，状态栏的大小会随着窗口的大小而变化。在本文中，我们将看到如何固定状态栏的大小，这样，如果窗口大小发生变化，它就不会改变状态栏的大小。

为了做到这一点，我们将使用`setFixedSize()`方法。

> **语法:** self.statusBar()。设置固定大小(宽度、高度)
> 
> **自变量:**取两个整数作为自变量，即宽度和高度。
> 
> **执行的操作:**它将固定大小设置到状态栏。

**代码:**

```
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

        # setting  border
        self.statusBar().setStyleSheet("border :3px solid black;")

        # setting fixed size to the status bar
        self.statusBar().setFixedSize(400, 40)

        # creating a label widget
        self.label_1 = QLabel("Fixed size", self)

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
![](img/548fd3eec1e863d7ba0d159242d15a66.png)