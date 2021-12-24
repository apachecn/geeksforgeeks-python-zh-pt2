# PyQt5 QDateedit–获取名称属性

> 原文:[https://www . geesforgeks . org/pyqt 5-qdatedit-get-name-property/](https://www.geeksforgeeks.org/pyqt5-qdateedit-getting-name-property/)

在本文中，我们将看到如何获取 QDateEdit 的 name 属性。Name 属性保存辅助技术看到的日期编辑名称。这是辅助技术(如屏幕阅读器)宣布给定日期编辑的主要名称。可以借助`setAccessibleName`方法进行设置。

为了做到这一点，我们对 QDateEdit 对象使用`accessibleName`方法

> **语法:** date.accessibleName()
> 
> **论证:**不需要论证
> 
> **返回:**返回字符串

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

        # text
        text = "Geek date edit"

        # setting name
        date.setAccessibleName(text)

        # creating a label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry
        label.setGeometry(100, 150, 200, 60)

        # making label multiline
        label.setWordWrap(True)

        # getting name property
        value = date.accessibleName()

        # setting text to the label
        label.setText("Name : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/bd083f01f01c4cf0e24578f145e43129.png)