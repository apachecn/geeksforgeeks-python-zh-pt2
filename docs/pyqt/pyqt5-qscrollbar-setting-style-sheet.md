# PyQt5 QScrollBar–设置样式表

> 原文:[https://www . geesforgeks . org/pyqt5-qscrollbar-setting-style-sheet/](https://www.geeksforgeeks.org/pyqt5-qscrollbar-setting-style-sheet/)

在本文中，我们将看到如何为 QScrollBar 设置样式表。QScrollBar 是一个控件，它使用户能够访问比用于显示文档的小部件更大的文档部分。滑块是条内的可滚动对象。样式表是用来使外观更好的属性，即通过创建定制的设计。

> 为此，我们将对滚动条对象使用`setStyleSheet`方法。
> 
> **语法:**滚动.设置样式表(工作表)
> 
> **自变量:**以字符串为自变量
> 
> **返回:**返回无

下面是示例样式表代码

```py
QScrollBar
{
background : lightgreen;
}
QScrollBar::handle
{
background : pink;
}
QScrollBar::handle::pressed
{
background : red;
}

```

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

        # setting style sheet
        scroll.setStyleSheet("QScrollBar"
                             "{"
                             "background : lightgreen;"
                             "}"
                             "QScrollBar::handle"
                             "{"
                             "background : pink;"
                             "}"
                             "QScrollBar::handle::pressed"
                             "{"
                             "background : red;"
                             "}"
                             )

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

<video class="wp-video-shortcode" id="video-462312-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200730015042/Python-2020-07-30-01-50-23.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200730015042/Python-2020-07-30-01-50-23.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200730015042/Python-2020-07-30-01-50-23.mp4)</video>