# pyqt 5–阻止按钮信号

> 原文:[https://www . geeksforgeeks . org/pyqt 5-按钮信号阻断/](https://www.geeksforgeeks.org/pyqt5-block-signals-of-push-button/)

在这篇文章中，我们将看到如何阻止按钮的信号，阻止信号意味着停止按钮来完成他分配的任务。它用于使按钮失效。

为了做到这一点，我们将使用属于`QObject class`的`**blockSignals**`方法。

> **语法:**按钮。块信号(真)
> 
> **自变量:**它以 bool 为自变量。
> 
> **执行动作:**阻断按钮信号。

**代码:**

```py
# importing libraries
from PyQt5.QtWidgets import * 
from PyQt5.QtGui import * 
from PyQt5.QtCore import * 
import sys

class Window(QMainWindow):
    def __init__(self):
        super().__init__()

        # setting title
        self.setWindowTitle("Python ")

        # setting geometry
        self.setGeometry(100, 100, 600, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for widgets
    def UiComponents(self):

        # creating a push button
        button = QPushButton("CLICK", self)

        # setting geometry of button
        button.setGeometry(200, 150, 100, 30)

        # adding action to a button
        button.clicked.connect(self.clickme)

        # blocking signals of the button
        button.blockSignals(True)

    # action method
    def clickme(self):

        # printing pressed
        print("pressed")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![pyqt-disable-button](img/21b7a656b915e0da25753bc8810edfc2.png)
当点击此按钮时，什么都不会发生。