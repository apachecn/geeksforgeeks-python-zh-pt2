# PyQt5 QScrollBar–为其设置图形效果

> 原文:[https://www . geesforgeks . org/pyqt5-qscrollbar-setting-graphic-effect-to-it/](https://www.geeksforgeeks.org/pyqt5-qscrollbar-setting-graphic-effect-to-it/)

在本文中，我们将了解如何为 QScrollBar 设置图形效果。QScrollBar 是一个控件，它使用户能够访问比用于显示文档的小部件更大的文档部分。滑块是条内的可滚动对象。setGraphicsEffect 函数用于设置滚动条的图形效果。将效果设置为小部件的效果。如果滚动条上已经安装了效果，QWidget 将在安装新效果之前删除现有效果。

> 为此，我们将对滚动条对象使用`setGraphicsEffect`方法。
> 
> **语法:** scroll.setGraphicsEffect(图形)
> 
> **自变量:**它以 QGraphicsEffect 对象为自变量
> 
> **返回:**返回无

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

        # QGraphicsEffect
        graphic = QGraphicsBlurEffect(self)

        # setting graphic effect to the scroll bar
        scroll.setGraphicsEffect(graphic)

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

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/8001958ecc072a91ae1f6c8257707279.png)