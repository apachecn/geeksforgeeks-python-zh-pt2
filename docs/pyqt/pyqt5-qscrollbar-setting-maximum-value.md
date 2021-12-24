# PyQt5 QScrollBar–设置最大值

> 原文:[https://www . geesforgeks . org/pyqt5-qscrollbar-setting-maximum-value/](https://www.geeksforgeeks.org/pyqt5-qscrollbar-setting-maximum-value/)

在本文中，我们将了解如何设置 QScrollBar 的最大值。QScrollBar 是一个控件，它使用户能够访问比用于显示文档的小部件更大的文档部分。滑块是条内的可滚动对象。默认情况下，值的范围为 0 到 99。数值基本上取决于滑块的位置，滚动条的数值根据滑块的位置而变化，数值在滑块下降时增加，在滑块上升时减少。可以借助`setValue`方法编程设置。最大值是不能为其设置任何值的值。

> 为此，我们将对滚动条对象使用`setMaximum`方法。
> 
> **语法:**滚动。设置最大值(n)
> 
> **自变量:**以整数为自变量
> 
> **返回:**返回无

下面是实现

```
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

        # setting maximum value of scroll bar
        scroll.setMaximum(200)

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

<video class="wp-video-shortcode" id="video-460866-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200728025535/Python-2020-07-28-02-55-17.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200728025535/Python-2020-07-28-02-55-17.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200728025535/Python-2020-07-28-02-55-17.mp4)</video>