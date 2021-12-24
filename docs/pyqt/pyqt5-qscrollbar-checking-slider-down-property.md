# PyQt5 QScrollBar–检查滑块向下属性

> 原文:[https://www . geesforgeks . org/pyqt5-qscrollbar-checking-slider-down-property/](https://www.geeksforgeeks.org/pyqt5-qscrollbar-checking-slider-down-property/)

在本文中，我们将看到如何检查 QScrollBar 的向下滑动属性。QScrollBar 是一个控件，它使用户能够访问比用于显示文档的小部件更大的文档部分。滑块是条内的可滚动对象。此属性决定滑块是否被按下。该属性由子类设置，以便让抽象滑块知道跟踪是否有任何效果。更改滑块下移属性会发出滑块被按下和滑块被释放的信号。可以借助 setSliderDown 方法进行设置。

> 为此，我们将对滚动条对象使用 isSliderDown 方法。
> **语法:**scroll . issliderdown()
> **参数:**不需要参数
> **返回:**返回 bool

下面是实现

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

        # setting slider down
        scroll.setSliderDown(True)

        # creating a label
        label = QLabel("GeesforGeeks", self)

        # setting geometry to the label
        label.setGeometry(200, 100, 300, 80)

        # making label multi line
        label.setWordWrap(True)

        # checking if slider is down
        value = scroll.isSliderDown()

        # setting text to the label
        label.setText("Is Slider Down: " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/0b518729eab6094fb0c8684b97631bdf.png)