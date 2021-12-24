# PyQt5 QScrollBar–设置倒置外观属性

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qscrollbar-设置-反转-外观-属性/](https://www.geeksforgeeks.org/pyqt5-qscrollbar-setting-inverted-appearance-property/)

在本文中，我们将看到如何设置 QScrollBar 的反转外观属性。QScrollBar 是一个控件，它使用户能够访问比用于显示文档的小部件更大的文档部分。滑块是条内的可滚动对象。此属性决定滑块是否显示反转的值。如果此属性为 false(默认值)，滚动条的最小值和最大值将显示在其经典位置。如果该值为真，则最小值和最大值出现在相反的位置。

> 为此，我们将对滚动条对象使用`setInvertedAppearance`方法。
> 
> **语法:**滚动。设置反转显示(真)
> 
> **自变量:**它以布尔为自变量
> 
> **返回:**返回无

下面是实现

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

        # setting inverted appearance
        scroll.setInvertedAppearance(True)

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

<video class="wp-video-shortcode" id="video-461929-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200729000742/Python-2020-07-29-00-07-12.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200729000742/Python-2020-07-29-00-07-12.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200729000742/Python-2020-07-29-00-07-12.mp4)</video>