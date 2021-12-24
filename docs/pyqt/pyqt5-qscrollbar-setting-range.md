# PyQt5 QScrollBar–设置范围

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qscrollbar-setting-range/](https://www.geeksforgeeks.org/pyqt5-qscrollbar-setting-range/)

在本文中，我们将了解如何设置 QScrollBar 的范围。QScrollBar 是一个控件，它使用户能够访问比用于显示文档的小部件更大的文档部分。滑块是条内的可滚动对象。默认情况下，值的范围为 0 到 99。数值基本上取决于滑块的位置，滚动条的数值根据滑块的位置而变化，数值在滑块下降时增加，在滑块上升时减少。可以借助`setValue`方法编程设置。范围基本上是最小值和最大值的组合。

> 为此，我们将对滚动条对象使用`setRange`方法。
> 
> **语法:** scroll.setRange(n，m)
> 
> **自变量:**取两个整数作为自变量
> 
> **返回:**返回无

下面是实现

```py
# importing libraries
from PyQt5.QtWidgets import * 
from PyQt5 import QtCore, QtGui
from PyQt5.QtGui import * 
from PyQt5.QtCore import * import sys

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

        # setting range of scroll bar
        scroll.setRange(200, 250)

        # making its background color to green
        scroll.setStyleSheet("background : lightgrey;")

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

            # getting current value
            value = scroll.value()

            # setting text to the label
            label.setText("Current Value : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-460862-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200728030117/Python-2020-07-28-03-00-52.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200728030117/Python-2020-07-28-03-00-52.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200728030117/Python-2020-07-28-03-00-52.mp4)</video>