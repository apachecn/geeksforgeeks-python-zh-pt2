# PyQt5 可滚动标签–获取标签部分的工具提示文本

> 原文:[https://www . geesforgeks . org/pyqt 5-可滚动-标签-获取-工具-提示-标签文本-零件/](https://www.geeksforgeeks.org/pyqt5-scrollable-label-getting-tool-tip-text-of-the-label-part/)

在本文中，我们将看到如何获得滚动标签的标签部分的工具提示文本，当我们知道我们可以通过继承一个滚动类并在其中制作标签来制作可滚动标签时，但是当我们将工具提示设置为类对象时，工具提示也将设置为整个小部件，即标签和滚动条。为了添加工具提示标签部分，我们只需要覆盖对象的功能。

> 实施步骤–
> 
> 1.创建一个继承 QScrollArea
> 2 的新类。班级内部创建垂直布局
> 3。创建一个标签，使其多行，并将其添加到布局
> 5。超越标签
> 6 的设置文本和文本方法。Over-ride setToolTip 方法将工具提示添加到标签，ToolTip 方法获取工具提示
> 7。在主窗口类中创建该类的对象，并为其设置文本
> 8。借助`setToolTip`方法
> 9 给对象添加工具提示。借助`toolTip`方法
> 10 检索工具提示文本。创建另一个标签以显示工具提示文本

下面是实现

```py
# importing libraries
from PyQt5.QtWidgets import * 
from PyQt5 import QtCore, QtGui
from PyQt5.QtGui import * 
from PyQt5.QtCore import * 
import sys

# class for scrollable label
class ScrollLabel(QScrollArea):

    # constructor
    def __init__(self, *args, **kwargs):
        QScrollArea.__init__(self, *args, **kwargs)

        # making widget resizable
        self.setWidgetResizable(True)

        # making qwidget object
        content = QWidget(self)
        self.setWidget(content)

        # vertical box layout
        lay = QVBoxLayout(content)

        # creating label
        self.label = QLabel(content)

        # making label multi-line
        self.label.setWordWrap(True)

        # adding label to the layout
        lay.addWidget(self.label)

    # the setText method
    def setText(self, text):
        # setting text to the label
        self.label.setText(text)

    # getting text method
    def text(self):
        # getting text of the label
        get_text = self.label.text()

        # return the text
        return get_text

    # overriding setToolTip method
    def setToolTip(self, text):
        # setting tool tip to the label
        self.label.setToolTip(text)

    # overriding toolTip method
    def toolTip(self):

        # returning tool tip text
        return self.label.toolTip()

class Window(QMainWindow):

    def __init__(self):
        super().__init__()

        # setting title
        self.setWindowTitle("Python ")

        # setting geometry
        self.setGeometry(100, 100, 600, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for widgets
    def UiComponents(self):
        # text to show in label
        text = "There are so many options provided by Python to develop GUI " \
               " There are so many options provided by Python to develop GUI" \
               " There are so many options provided by Python to develop GUI"

        # creating scroll label
        label = ScrollLabel(self)

        # setting text to the label
        label.setText(text)

        # setting geometry
        label.setGeometry(100, 100, 150, 80)

        # setting tool tip
        label.setToolTip("It is tool tip")

        # getting the tool tip
        tip = label.toolTip()

        # creating another label to show the tool tip
        result = QLabel("Tool tip : " + tip, self)

        # setting geometry to the label
        result.setGeometry(150, 200, 200, 30)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/5bc8956dec86fdd2d400ffe8d877d653.png)