# pyqt 5 qscroll bar–释放游标

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qscrollbar-get-cursor/](https://www.geeksforgeeks.org/pyqt5-qscrollbar-getting-cursor/)

在本文中，我们将看到如何获得 QScrollBar 的游标。QScrollBar 是一个控件，它使用户能够访问比用于显示文档的小部件更大的文档部分。滑块是条内的可滚动对象。设置光标是指在滚动条上设置专门的光标，该光标仅用于滚动条，可以借助`setCursor`方法进行设置。

> 为此，我们将对滚动条对象使用`cursor`方法。
> 
> **语法:**滚动光标()
> 
> **论证:**不需要论证
> 
> **返回:**返回 QCursor 对象

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

        scroll = QScrollBar(self)

        # setting geometry of the scroll bar
        scroll.setGeometry(100, 50, 30, 200)

        # making its background color to green
        scroll.setStyleSheet("background : lightgrey;")

        # setting cursor to the scroll bar
        scroll.setCursor(Qt.OpenHandCursor)

        # creating a label
        label = QLabel("GeesforGeeks", self)

        # setting geometry to the label
        label.setGeometry(200, 100, 300, 80)

        # making label multi line
        label.setWordWrap(True)

        # getting value changed signal
        scroll.valueChanged.connect(lambda: do_action())

        # method called when signal is emitted
        def do_action():

            # setting text to the label
            label.setText("Current Value : " + str(scroll.value()))

        # getting cursor
        value = scroll.cursor()

        # setting text to the label
        label.setText("Cursor : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/58c4bda5e6e0a2c8fbcdb16f5090a227.png)