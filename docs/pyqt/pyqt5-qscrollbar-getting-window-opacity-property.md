# PyQt5 QScrollBar–获取窗口不透明度属性

> 原文:[https://www . geeksforgeeks . org/pyqt5-qscrollbar-get-window-不透明度-property/](https://www.geeksforgeeks.org/pyqt5-qscrollbar-getting-window-opacity-property/)

在本文中，我们将看到如何获得 QScrollBar 的窗口不透明度属性。QScrollBar 是一个控件，它使用户能够访问比用于显示文档的小部件更大的文档部分。滑块是条内的可滚动对象。此属性保持窗口的不透明度。不透明度的有效范围是从 1.0(完全不透明)到 0.0(完全透明)。可以借助`setWindowOpacity`方法进行设置。

> 为此，我们将对滚动条对象使用`windowOpacity`方法。
> 
> **语法:** scroll.windowOpacity()
> 
> **论证:**不需要论证
> 
> **返回:**返回浮点值

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

        # setting window opacity property
        scroll.setWindowOpacity(1.0)

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

        # getting window opacity property
        value = scroll.windowOpacity()

        # setting text to the label
        label.setText("Window Opacity Property : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/a255500158f51d028d2b2c553f461f97.png)