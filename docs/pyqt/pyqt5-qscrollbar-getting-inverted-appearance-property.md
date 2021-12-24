# PyQt5 QScrollBar–获得倒置外观属性

> 原文:[https://www . geesforgeks . org/pyqt5-qscrollbar-get-inverted-appearance-property/](https://www.geeksforgeeks.org/pyqt5-qscrollbar-getting-inverted-appearance-property/)

在本文中，我们将看到如何获得 QScrollBar 的反转外观属性。QScrollBar 是一个控件，它使用户能够访问比用于显示文档的小部件更大的文档部分。滑块是条内的可滚动对象。此属性决定滑块是否显示反转的值。如果此属性为 false(默认值)，滚动条的最小值和最大值将显示在其经典位置。如果该值为真，则最小值和最大值出现在相反的位置。可以借助`setInvertedAppearance`方法进行设置。

> 为此，我们将对滚动条对象使用`invertedAppearance`方法。
> 
> **语法:**滚动。反转显示()
> 
> **论证:**不需要论证
> 
> **返回:**返回 bool

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

        # getting inverted appearance property
        value = scroll.invertedAppearance()

        # setting text to the label
        label.setText("Inverted Appearance : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/e0d288fa7b712c2ae8ed5cabb1cd5d5f.png)