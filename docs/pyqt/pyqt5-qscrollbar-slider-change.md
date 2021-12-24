# pyqt 5 qscroll bar–slider change

> 哎哎哎:# t0]https://www . geeksforgeeks . org/pyqt 5-qscrollbar-slider-change/

在本文中，我们将了解如何更改 QScrollBar 的滑块表示。QScrollBar 是一个控件，它使用户能够访问比用于显示文档的小部件更大的文档部分。滑块是条内的可滚动对象。基本上有以下四种滑块变化选项:滑块范围变化、滑块方向变化、滑块步长变化和滑块值变化。

> 为此，我们将对滚动条对象使用 sliderChange 方法。
> **语法:**scroll . slider change(slider change)
> **参数:**以滑块变化对象为参数
> **返回:**返回 None

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

        # setting slider change
        scroll.sliderChange(QAbstractSlider.SliderOrientationChange)

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

![](img/dc5ec37432a3d2379c7abb9b886e5c7a.png)