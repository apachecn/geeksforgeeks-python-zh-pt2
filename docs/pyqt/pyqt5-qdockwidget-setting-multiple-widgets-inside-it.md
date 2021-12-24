# PyQt5 QDockWidget–在其中设置多个小部件

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdock widget-setting-multi-widgets-inside-it/](https://www.geeksforgeeks.org/pyqt5-qdockwidget-setting-multiple-widgets-inside-it/)

在本文中，我们将看到如何向 QDockWidget 添加/设置多个小部件。QDockWidget 提供了 DockWidget 的概念，也称为工具选项板或实用程序窗口。停靠窗口是放置在 QMainWindow(原始窗口)中央小部件周围的停靠小部件区域中的辅助窗口。我们使用 setWidget 方法向 dock Widget 添加/设置 widget。但这仅用于设置单个小部件。

> 为了在其中设置多个小部件，我们必须执行以下操作
> 1。创建主窗口类
> 2。在该类中创建一个 QDockWidget 对象并设置其属性
> 3。创建一个 QWidget 对象
> 4。创建一个 QLayout 对象
> 5。创建我们想要添加到 QDockWidget
> 6 中的各种 widget 对象。借助 addWidget 方法
> 7，将这些小部件添加到之前创建的布局中。借助 setLayout 方法
> 8 将此 laypout 设置为 QWidget 对象。借助设置窗口小部件方法
> ，将该窗口小部件对象设置为窗口小部件对象

下面是实现

## 蟒蛇 3

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

        # creating dock widget
        dock = QDockWidget(self)

        # setting title to the doc widget
        dock.setWindowTitle("GfG ")

        # creating a QWidget object
        widget = QWidget(self)

        # creating a vertical box layout
        layout = QVBoxLayout(self)

        # push button 1
        push1 = QPushButton("A", self)

        # push button 2
        push2 = QPushButton("B", self)

        # push button 3
        push3 = QPushButton("C", self)

        # adding these buttons to the layout
        layout.addWidget(push1)
        layout.addWidget(push2)
        layout.addWidget(push3)

        # setting the layout to the widget
        widget.setLayout(layout)

        # adding widget to the layout
        dock.setWidget(widget)

        # creating a label
        label = QLabel("GeesforGeeks", self)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 80)

        # making label multi line
        label.setWordWrap(True)

        # setting geometry tot he dock widget
        dock.setGeometry(100, 0, 200, 30)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-460009-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200725041003/Python-2020-07-25-04-09-34.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200725041003/Python-2020-07-25-04-09-34.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200725041003/Python-2020-07-25-04-09-34.mp4)</video>