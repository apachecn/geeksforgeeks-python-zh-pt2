# PYqt5 QDateedit–获取按钮符号

> 原文:[https://www . geesforgeks . org/pyqt 5-qdatedit-get-button-symbols/](https://www.geeksforgeeks.org/pyqt5-qdateedit-getting-button-symbols/)

在本文中，我们将看到如何获得 QDateEdit 的按钮符号。日期编辑可以使用两个箭头按钮来增加和减少日期，我们可以借助`setButtonSymbols`方法移除按钮，即使移除按钮，也不会对日期编辑的功能产生重大影响。

为了做到这一点，我们对 QDateEdit 对象使用`buttonSymbols`方法

> **语法:**日期.按钮符号()
> 
> **论证:**不需要论证
> 
> **返回:**返回按钮符号对象，但打印时显示其相应值

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

        # creating a label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry
        label.setGeometry(100, 150, 200, 60)

        # making label multiline
        label.setWordWrap(True)

        # getting button symbol
        value = date.buttonSymbols()

        # setting text to the label
        label.setText("Button Symbol : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/39c9182786a7d105825ed67949946b19.png)