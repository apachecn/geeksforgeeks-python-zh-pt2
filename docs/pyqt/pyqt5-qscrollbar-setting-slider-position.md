# PyQt5 QScrollBar–设置滑块位置

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qscrollbar-设置-滑块-位置/](https://www.geeksforgeeks.org/pyqt5-qscrollbar-setting-slider-position/)

在本文中，我们将看到如何在 QScrollBar 中以编程方式设置滑块的位置。QScrollBar 是一个控件，它使用户能够访问比用于显示文档的小部件更大的文档部分。滑块是条内的可滚动对象。我们可以借助鼠标和键盘改变它的位置。

> 为此，我们将对滚动条对象使用 setSliderPosition 方法。
> **语法:**scroll . setsliderposition(n)
> **参数:**以整数为参数
> **返回:**不返回

**示例:**下面是实现

## 蟒蛇 3

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

        scroll = QScrollBar(self)

        # setting geometry of the scroll bar
        scroll.setGeometry(100, 50, 30, 200)

        # making its background color to green
        scroll.setStyleSheet("background : lightgrey;")

        # setting slider position
        scroll.setSliderPosition(50)

        # creating a label
        label = QLabel("GeesforGeeks", self)

        # setting geometry to the label
        label.setGeometry(200, 100, 300, 80)

        # making label multi line
        label.setWordWrap(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/63a1f58a402794fd56372bbd3e31a2a7.png)