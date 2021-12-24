# pyqt 5 qdateedit–向外方向

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdateedit-get-direction/](https://www.geeksforgeeks.org/pyqt5-qdateedit-getting-direction/)

在本文中，我们将了解如何获得日期编辑的方向。默认情况下，当我们创建日期时，编辑箭头按钮位于右侧，尽管我们可以通过`setLayoutDirection`方法更改布局方向来更改它。

为了做到这一点，我们对 QDateEdit 对象使用`layoutDirection`方法

> **语法:** date.layoutDirection()
> 
> **论证:**不需要论证
> 
> **返回:**它返回方向对象，但打印时会显示与之相关的值

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

        # creating a QDateEdit widget
        date = QDateEdit(self)

        # setting geometry of the date edit
        date.setGeometry(100, 100, 200, 40)

        # alignment
        a_flag = Qt.AlignCenter

        # setting alignment of date
        date.setAlignment(a_flag)

        # setting layout direction
        date.setLayoutDirection(Qt.RightToLeft)

        # creating a label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry
        label.setGeometry(100, 150, 250, 60)

        # making label multiline
        label.setWordWrap(True)

        # getting direction
        value = date.layoutDirection()

        # setting text to the label
        label.setText("Direction : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/1ada2cca937ee60da52f86ef471d5c69.png)