# PYqt 5 QDateedit–从中移除按钮

> 原文:[https://www . geesforgeks . org/pyqt 5-qdatedit-remove-buttons-from-it/](https://www.geeksforgeeks.org/pyqt5-qdateedit-removing-buttons-from-it/)

在本文中，我们将看到如何删除 QDateEdit 的按钮。日期编辑编辑可以使用两个箭头按钮来增加和减少日期，即使删除按钮也不会对日期编辑的功能产生重大影响。

为了做到这一点，我们对 QDateEdit 对象使用`setButtonSymbols`方法

> **语法:**日期.设置按钮符号(2)
> 
> **自变量:**以按钮符号对应值为自变量
> 
> **返回:**返回无

下面是实现

```
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

        # creating a QDateEdit widget
        date = QDateEdit(self)

        # setting geometry of the date edit
        date.setGeometry(100, 100, 150, 40)

        # removing button
        date.setButtonSymbols(2)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/6bf1e47e9d5b4638aa20174cdcda989f.png)