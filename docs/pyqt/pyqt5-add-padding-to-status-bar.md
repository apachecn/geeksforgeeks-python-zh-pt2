# PyQt5–向状态栏添加填充

> 原文:[https://www . geeksforgeeks . org/pyqt 5-添加-填充到状态栏/](https://www.geeksforgeeks.org/pyqt5-add-padding-to-status-bar/)

在本文中，我们将看到如何添加填充到状态栏。与没有填充的主窗口不同，状态栏允许我们设置填充。填充基本上是状态栏边框和内容之间的空间，我们可以用状态栏对象的`**setStyleSheet**`方法来设置这个大小。

**注意:**在状态栏中，填充仅适用于顶部和底部，不适用于左侧或右侧边缘。

> **语法:** self.statusBar()。set 样式表(“填充:15px”)
> 
> **自变量:**它以字符串为自变量。
> 
> **执行的操作:**为状态栏设置填充

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

        # setting  border and padding 
        self.statusBar().setStyleSheet("border :3px solid black; 
                                        padding: 15px;")

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
![](img/23bab80fe49a79166a8ce8cbc4035526.png)