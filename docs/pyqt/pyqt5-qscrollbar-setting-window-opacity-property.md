# PyQt5 QScrollBar–设置窗口不透明度属性

> 原文:[https://www . geesforgeks . org/pyqt5-qscrollbar-设置-窗口-不透明度-属性/](https://www.geeksforgeeks.org/pyqt5-qscrollbar-setting-window-opacity-property/)

在本文中，我们将看到如何将窗口不透明度属性设置为 QScrollBar。QScrollBar 是一个控件，它使用户能够访问比用于显示文档的小部件更大的文档部分。滑块是条内的可滚动对象。此属性保持窗口的不透明度。不透明度的有效范围是从 1.0(完全不透明)到 0.0(完全透明)。

**注意:**在 X11 上你需要有一个复合管理器在运行，并且 X11 特定的 _NET_WM_WINDOW_OPACITY 原子需要被你正在使用的窗口管理器支持。

> 为此，我们将对滚动条对象使用`setWindowOpacity`方法。
> 
> **语法:**滚动。设置窗口不透明度(n)
> 
> **自变量:**它以 float 为自变量
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

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/16318991e68e18d2a4cd6f92c1e2e717.png)