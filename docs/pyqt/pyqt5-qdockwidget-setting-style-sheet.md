# PYqt5 QDockWidget–设置样式表

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdockewidget-设置-样式表/](https://www.geeksforgeeks.org/pyqt5-qdockwidget-setting-style-sheet/)

在本文中，我们将看到如何为 QDockWidget 设置样式表。QDockWidget 提供了 DockWidget 的概念，也称为工具选项板或实用程序窗口。停靠窗口是放置在 QMainWindow(原始窗口)中央小部件周围的停靠小部件区域中的辅助窗口。样式表代表小部件的样式，即外观，它由颜色、间距、填充、边框特征组成

> 为此，我们将对 dock widget 对象使用`setStyleSheet`方法。
> 
> **语法:**dock . set 样式表(样式)
> 
> **自变量:**以字符串为自变量
> 
> **返回:**返回无

下面是示例样式表代码

```py
QDockWidget
{
background : lightgreen;
}
QDockWidget::title
{
background : lightblue;
}
QDockWidget QPushButton
{
border : 2px solid black;
background : darkgreen;
}

```

**注意:**这里我们使用了 QDockWidget::qbutton 因为我们在 dock 中添加了按钮，所以如果添加了任何其他 Widget，我们可以使用其他 widget 名称。

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

        # creating dock widget
        dock = QDockWidget(self)

        # setting title to the doc widget
        dock.setWindowTitle("GfG Title")

        # creating a QWidget object
        widget = QWidget(self)

        # creating a vertical box layout
        layout = QVBoxLayout(self)

        # push button 1
        push1 = QPushButton("A", self)

        # push button 2
        push2 = QPushButton("B", self)

        # adding these buttons to the layout
        layout.addWidget(push1)
        layout.addWidget(push2)

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

        # setting geometry to the dock widget
        dock.setGeometry(100, 0, 200, 30)

        # setting style sheet to the  dock widget
        dock.setStyleSheet("QDockWidget"
                           "{"
                           "background : lightgreen;"
                           "}"
                           "QDockWidget::title"
                           "{"
                           "background : lightblue;"
                           "}"
                           "QDockWidget QPushButton"
                           "{"
                           "border : 2px solid black;"
                           "background : darkgreen;"
                           "}"
                           )

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/2e3c93c47734ba11d92e5cd724533a66.png)