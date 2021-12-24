# 关闭 PyQt5 中的()方法

> 原文:[https://www.geeksforgeeks.org/close-method-in-pyqt5/](https://www.geeksforgeeks.org/close-method-in-pyqt5/)

在本文中，我们将看到如何使用属于`QWidget class`的`close()`方法，该方法用于在 PyQt5 应用程序中关闭窗口。换句话说，通过`close()`方法，窗户不用手动关闭就可以关闭。

> **句法:** self.close()
> 
> **论证:**无需论证。

**代号:**

```py
# importing the required libraries

from PyQt5.QtWidgets import * 
from PyQt5 import QtCore
from PyQt5 import QtGui
import sys
import time

class Window(QMainWindow):
    def __init__(self):
        super().__init__()

        # set the title
        self.setWindowTitle("Close")

        # setting  the geometry of window
        self.setGeometry(0, 0, 400, 300)

        # creating a label widget
        self.label = QLabel("Icon is set", self)

        # moving position
        self.label.move(100, 100)

        # setting up border
        self.label.setStyleSheet("border: 1px solid black;")

        # show all the widgets
        self.show()

        # waiting for 2 second
        time.sleep(2)

        # closing the window
        self.close()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

这将打开窗口，2 秒钟后自动关闭窗口。